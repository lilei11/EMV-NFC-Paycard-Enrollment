## EMV NFC Paycard Enrollment [![Build Status](https://travis-ci.org/devnied/EMV-NFC-Paycard-Enrollment.png?branch=master)](https://travis-ci.org/devnied/EMV-NFC-Paycard-Enrollment) [![Coverage Status](https://coveralls.io/repos/devnied/EMV-NFC-Paycard-Enrollment/badge.png)](https://coveralls.io/r/devnied/EMV-NFC-Paycard-Enrollment)
### Description

Java library used to read and extract data from NFC EMV paycard.

Sample app available on the [Play Store](https://play.google.com/store/apps/details?id=com.github.devnied.emvnfccard)

### Getting started

First you need to create a custom Provider to exchange APDU to NFC EMV card.
```java
public class YourProvider implements IProvider {

  @Override
  public byte[] transceive(final byte[] pCommand) {
	 // implement this
  }
}
```
After that, create an instance of a parser and read the card.
```java
IProvider prov = new YourProvider();
// Create parser
EMVParser parser = new EMVParser(prov, true);
// Read card
EMVCard card = parser.readEmvCard();
```
card object contains all data read (Aid, card number, expiration date, card type, payments history)

### Screens

[![Sample demo](https://raw.githubusercontent.com/devnied/EMV-NFC-Paycard-Enrollment/master/images/demo.gif)](https://raw.githubusercontent.com/devnied/EMV-NFC-Paycard-Enrollment/master/images/demo.gif)

## Dependencies

If you are not using Maven or some other dependency management tool that can understand Maven repositories, the list below is what you need to run bit-lib4j.

**Runtime Dependencies**
* commons-lang3 3.1
* bit-lib4j 1.4.5

## Bugs

Please report bugs and feature requests to the GitHub issue tracker.<br/>
Forks and Pull Requests are also welcome.

## Author

**Millau Julien**

+ [http://twitter.com/devnied](http://twitter.com/devnied)
+ [http://github.com/devnied](http://github.com/devnied)


## Copyright and license

Copyright 2014 Millau Julien.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this work except in compliance with the License.
You may obtain a copy of the License in the LICENSE file, or at:

  [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[![Analytics](https://ga-beacon.appspot.com/UA-19411627-6/MV-NFC-Paycard-Enrollment)](https://github.com/igrigorik/ga-beacon)