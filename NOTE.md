# Taxi-Taxi@SG

```
DYLD_INSERT_LIBRARIES=dumpdecrypted.dylib /var/mobile/Containers/Bundle/Application/*/taxiapp-PROD.app/taxiapp-PROD

Hopper/IDA Pro

cycript -p #{pid}

@import com.saurik.substrate.MS
var oldm = {};
MS.hookMessage(ZipArchive, @selector(UnzipOpenFile:Password:), function(file, password) {
    NSLog("Password: " + password);
    return oldm->call(this, file, password);
}, oldm)
```

# LLDB

http://versprite.com/og/ios-reverse-engineering-part-one-configuring-lldb/

```
hdiutil attach /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport/9.0/DeveloperDiskImage.dmg
cp /Volumes/DeveloperDiskImage/usr/bin/debugserver ./
# Generates Entitlement
codesign -s - --entitlements entitlements.plist -f debugserver
```