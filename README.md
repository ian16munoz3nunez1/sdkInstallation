# SDK Installation

## Windows Installation

### Pro-X

1. Install OS

2. Install java version from `\\10.89.159.16\Work\IanMunozNunez` and set the following environment variable `JAVA_HOME` to

```
C:\Program Files\ojdkbuild\java-1.8.0-openjdk-1.8.0.332-1
```

3. Install UPOS (download GA from [UPOS](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-commonpackages-sitearea))

4. Extract `C:\POS\drivers\javaxusb_lights\javaxusb_lights.zip`

5. Copy `C:\POS\drivers\javaxusb_lights\*` to `C:\POS\drivers\oem\psc`

6. Install ***javaxusb_lights*** driver using

```
C:\POS\bin\aipdifx.exe -i C:\POS\drivers\javaxusb_lights\javaxusb_lights.inf -v
```

7. Install ***javaxusb_oem_psc*** driver using

```
C:\POS\bin\aipdifx.exe -i C:\POS\drivers\oem\psc\javaxusb_oem_psc.inf -v
```
8. Install SDK

9. Install ***TTEC*** drivers (Download driver from [TTEC](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-selfcheckout))

10. Overwrite the value of `TCX_SDK_EXT` variable for

```
C:\Program Files (x86)\TOSHIBA\JavaPOS\JavaLibrary\CmnJLog.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\JNI\TECInterfaceJni.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Library\commons-io-2.6.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Library\javapos-config-loader-2.2.0.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Library\javapos-contracts-1.14.3.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Library\javapos-controls-1.14.1.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Library\JposEntryEditor.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Library\swing-layout-1.0.3.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Service\TECLightService.jar;C:\Program Files (x86)\TOSHIBA\JavaPOS\Service\TECPOSPrinterService.jar;
```

11. Add `jpos.xml` file to `C:\POS\JavaPOS`

12. Add certificates folder `keystore` to `C:\TCx SDK\DeviceBroker\conf\`

13. Add keystore certificates

14. Reboot the system

15. Validate that the SDK service is running

16. Open ***Message Browser*** running `start-message-browser.bat` in `C:\TCx SDK\DeviceBroker\bin` as administrator

### System 7

1. Install OS

2. Install java version from `\\10.89.159.16\Work\IanMunozNunez` and set the following environment variable `JAVA_HOME` to

```
C:\Program Files\ojdkbuild\java-1.8.0-openjdk-1.8.0.332-1
```

3. Install UPOS (download GA from [UPOS](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-commonpackages-sitearea))

4. Extract `C:\POS\drivers\javaxusb_lights\javaxusb_lights.zip`

5. Copy `C:\POS\drivers\javaxusb_lights\*` to `C:\POS\drivers\oem\psc`

6. Install ***javaxusb_lights*** driver using

```
C:\POS\bin\aipdifx.exe -i C:\POS\drivers\javaxusb_lights\javaxusb_lights.inf -v
```

7. Install ***javaxusb_oem_psc*** driver using

```
C:\POS\bin\aipdifx.exe -i C:\POS\drivers\oem\psc\javaxusb_oem_psc.inf -v
```
8. Install SDK

9. Install third party drivers for cash devices (BCR/BNR)

10. Add

```
C:\TCx SDK\DeviceBroker\lib\dll
```

and

```
C:\TCx SDK\DeviceBroker\lib\extn
```

to `PATH`

11. Add `jpos.xml` file to `C:\POS\JavaPOS`

12. Create an empty file in `C:\POS\JavaPOS\config\enableLights.conf`

13. Check serial port in ***Device Manager*** and change the value in `jpos.xml` file (`value="COMx"`)

14. Add certificates folder `keystore` to `C:\TCx SDK\DeviceBroker\conf\`

15. Reboot the system

16. Validate that the SDK service is running

17. Open ***Message Browser*** running `start-message-browser.bat` in `C:\TCx SDK\DeviceBroker\bin` as administrator

## Linux installation

### System 7

1. Install OS

2. Update the system with

    1. `sudo apt update`
    2. `sudo apt upgrade`
    3. `sudo apt dist-upgrade`
    4. `sudo apt autoremove`

3. Install java 8 running

```
sudo apt install openjdk-8-jdk
```

4. Install `toshibaposs-gcc` deb file with

```
sudo apt install ./<filename>.deb
```

Download UPOS deb package [here](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-commonpackages-sitearea)

5. Install `toshiba-javapos` deb file with

```
sudo apt install ./<filename>.deb
```

Download UPOS deb package [here](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-commonpackages-sitearea)

6. Install `javax-usb` deb file with

```
sudo apt install ./<filename>.deb
```

Download UPOS deb package [here](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-commonpackages-sitearea)

7. Install `javax-usb-ri` deb file with

```
sudo apt install ./<filename>.
```

Download UPOS deb package [here](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-commonpackages-sitearea)

8. Install `javax-usb-ri-linux` deb file with

```
sudo apt install ./<filename>.deb
```

Download UPOS deb package [here](https://commerce.toshiba.com/wps/portal/marketing/?urile=wcm:path:/en-us/home/support/product-support/support-hardware/support-commonpackages-sitearea)

9. Install ***SDK***

10. Add the line below to `/opt/tgcs/device-broker/bin/start-broker.sh`

```
export LD_LIBRARY_PATH="${LD_LIBRARY_PATH}:${TCX_SDK_HOME}/lib/so/:/usr/lib/jvm/java-8-openjdk-amd64/jre/lib/amd64/:"
```

11. Add certificates folder `keystore` to `/opt/tgcs/device-broker/conf/`

12. Reboot the system

13. Check that ***SDK Service*** is running with

```
ps aux | grep java
```

### Notes

To kill processes use

```
sudo kill <PID>
```
