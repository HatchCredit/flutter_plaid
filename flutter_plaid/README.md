Flutter for Plaid Link

[![pub](https://img.shields.io/pub/v/flutter_plaid.svg)](https://pub.dev/packages/flutter_plaid)

## Usage

```dart
class _Example extends State {
  
  showPlaidView() {
    bool plaidSandbox = false;
    
    Configuration configuration = Configuration(
        plaidPublicKey: 'yourPublicKey',
        plaidBaseUrl: 'https://cdn.plaid.com/link/v2/stable/link.html',
        plaidEnvironment: plaidSandbox ? 'sandbox' : 'production',
        environmentPlaidPathAccessToken:
            'https://sandbox.plaid.com/item/public_token/exchange',
        environmentPlaidPathStripeToken:
            'https://sandbox.plaid.com/processor/stripe/bank_account_token/create',
        plaidClientId: 'yourPlaidClientId',
        secret: plaidSandbox ? 'yourSecret' : '');

    FlutterPlaidApi flutterPlaidApi = FlutterPlaidApi(configuration);
    flutterPlaidApi.launch(context, (Result result) {
      ///handle result
    }, stripeToken: true);
  }

  @override
  Widget build(BuildContext context) {
    return Container();
  }
}

```