# Troubleshooting

#### My wallet doesn't detect my ANTv2 balance

Your wallet may not immediately detect your upgraded ANTv2 balance. In this case, you should be able to find documentation on how to add custom tokens to your wallet's interface. You will want to use `0xa117000000f279D81A1D3cc75430fAA017FA5A2e` as the token address.

For example, if you use Metamask, you can follow [this guide to add custom tokens](https://metamask.zendesk.com/hc/en-us/articles/360015489031-How-to-View-See-Your-Tokens-in-Metamask).

#### My wallet isn't connecting

Your wallet may be experiencing issues. If this issue persists, please reach out to us on [Discord](https://discord.com/invite/aragon).

{% hint style="info" %}
We are currently investigating issues with connecting to [WalletConnect](https://walletconnect.org/)-enabled wallets. We hope to enable WalletConnect soon.
{% endhint %}

#### My transactions aren't being propagated

You may not have specified a high enough gas price or your wallet may be experiencing issues.

If you're not familiar with the concept of gas on Ethereum, [ethgas.io](https://ethgas.io/) is a great primer. Your wallet will have built-in controls to help adjust the gas price used in your transactions so that they get mined in a timely fashion (for example, see [Metamask's documentation](https://metamask.zendesk.com/hc/en-us/articles/360015488771-How-to-Adjust-Gas-Price-and-Gas-Limit-)).

#### My transactions are failing

Please double check that your transaction has specified a high enough gas limit and that your account holds enough ETH. Using 250,000 as the gas limit for any transactions requested by the Upgrade Portal will be sufficient.

If you're not familiar with the concept of gas on Ethereum, [ethgas.io](https://ethgas.io/) is a great primer.
