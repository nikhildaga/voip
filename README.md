# voip

## Get device id
Launch app on phone
Get device token from console.  
e.g. ` 40cc4209 d0f3ac25 95a7e937 3282897b 211231ef ba66764c 6fd2befa b42076cb `


## Prepare Cert
Create VoIP Services Certificate from https://developer.apple.com/account/ios/certificate/

Open the keychain app on your mac and then export (right click then select Export) the certificate as a .p12 file.

Now, navigate to the folder where you exported this file and execute the following command:

`openssl pkcs12 -in YOUR_CERT.p12 -out voip.pem -nodes -clcerts`

This will generate voip.pem file 

## Install Houston
`sudo gem install -n /usr/local/bin houston`

## Send Notification
`sudo apn push "40cc4209 d0f3ac25 95a7e937 3282897b 211231ef ba66764c 6fd2befa b42076cb" -c voip.pem -m "hey"`  
replace above with correct device id


## Reference:
https://github.com/ianlin/react-native-voip-push-notification
http://www.nikola-breznjak.com/blog/ios/create-native-ios-app-can-receive-voip-push-notifications/
