CHANGELOG for 3.x
=================
## 3.0
* Use `rlanvin/php-ip` version 2 [Issue #43](https://github.com/Badcow/DNS/issues/43).
* Namespace `Badcow\DNS\Rdata\DNSSEC` is deprecated and deleted. [Issue #42](https://github.com/Badcow/DNS/issues/42).
* Deleted deprecated constants:
  * `\Badcow\DNS\Parser\Normaliser::COMMENTS_NONE`
  * `\Badcow\DNS\Parser\Normaliser::COMMENTS_END_OF_RECORD_ENTRY`
  * `\Badcow\DNS\Parser\Normaliser::COMMENTS_WITHIN_MULTILINE`
  * `\Badcow\DNS\Parser\Normaliser::COMMENTS_WITHOUT_RECORD_ENTRY`
  * `\Badcow\DNS\Parser\Normaliser::COMMENTS_ALL`
* Upgraded to PHPUnit 8.
* Deprecated and deleted method `RdataInterface::output()` in favour of `RdataInterface::toText()`.
* New `RdataInterface` methods:
  * `RdataInterface::toText()` same as `RdataInterface::output()`
  * `RdataInterface::fromText()` construct an Rdata object from an Rdata string.
  * `RdataInterface::toWire()` Return rdata in its wire format ready to be placed in DNS request/response packet.
  * `RdataInterface::fromWire()` construct an Rdata object from wire formatted Rdata.
  * `RdataInterface::getTypeCode()` return the IANA Resource Record type code.
* Enforce strict_types [Issue #37](https://github.com/Badcow/DNS/issues/37).
* Support more additional RDATA types [Issue #55](https://github.com/Badcow/DNS/issues/55):
  * AFSDB
  * CDNSKEY
  * CDS
  * CERT
  * CSYNC
  * DHCID
  * DLV
  * HIP
  * IPSECKEY
  * KEY
  * KX
  * NAPTR
  * NSEC3
  * NSEC3PARAM
  * RP
  * SIG
  * SSHFP
  * TA
  * TKEY
  * TLSA
  * TSIG
  * URI
* New Validator methods:
  * `Validator::isBase64Encoded()`
  * `Validator::isUnsignedInteger()`
  * `Validator::isBase16Encoded()`
  * `Validator::isBase32Encoded()`
  * `Validator::isBase32HexEncoded()`
* Deprecate and delete NSEC methods:
  * `NSEC::addTypeBitMap()` replaced with `NSEC::addType()`
  * `NSEC::clearTypeMap()` replaced with `NSEC::clearTypes()`
  * `NSEC::getTypeBitMaps()` replaced with `NSEC::getTypes()`
* Deleted ResourceRecord::__construct(); the same functionality has been moved to static method ResourceRecord::create();
* Rename class `Bacow\DNS\Rdata\TypeCodes` to `Badcow\DNS\Rdata\Types`.
* Delete class `Badcow\DNS\Parser\RDataTypes` as the same functionality exists in `Badcow\DNS\Rdata\Types`.
* Added the Unknown Record Type `Badcow\DNS\Rdata\UnknownType` which complies with [RFC 3597 - Handling of Unknown DNS Resource
  Record (RR) Types](https://tools.ietf.org/html/rfc3597).
* Deleted class `Badcow\DNS\IP\Toolbox`, moved all methods to `Badcow\DNS\IP\PTR`.