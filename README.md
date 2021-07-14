# digio-ios-sdk

## Create SDK configuration

>Step 1: Import the Digio module 

```sh
import DigioEsignSDK

```

>Step 2: Configure Digio instance

```sh
         DigioBuilder()
                .withController(viewController: self) /**  Mandatory:- pass your view controller here **/
                .setLogo(logo: "")   /**  Optional:- your logo link **/
                .setDocumentId(documentId: "docId") /** Mandatory:- Unique MandateId /Document ID  **/
                .setIdentifier(identifier: "email/phone")  /** Mandatory identifier **/
                .setTokenId(tokenId: "")   /** Optional: token id to bypass first factor authenticatio**/
                .setEnvironment(environment: DigioEnvironment.SANDBOX) /** Mandatory: SANDBOX / PRODUCTION **/
                .setServiceMode(serviceMode: DigioServiceMode.OTP) /** Mandatory **/
                .setAdditionalParams(additionalParams: additionalParam) /** optional use for eNach/mandate only **/
                .build()
```



### Handle SDK response
- Extend DigioEsignDelegate, add onDigioResponseSuccess & onDigioResponseFailure protocol stubs

```sh
extension YourViewController : DigioEsignDelegate {
      func onDigioResponseSuccess(response: String) {
          print("Success \(response)")
       }
 
      func onDigioResponseFailure(response: String) {
          print("Failure \(response)")
      }
  }

```


