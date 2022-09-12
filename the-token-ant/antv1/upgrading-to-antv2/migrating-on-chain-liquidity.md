# Migrating on-chain liquidity

ANTv1's on-chain liquidity has historically been concentrated across two platforms:

* Uniswap
* Balancer

## Uniswap

First, withdraw any ANTv1 liquidity you've provided. For example, from the [ANTv1/ETH UniswapV2 pool](https://app.uniswap.org/#/remove/0xfa19de406e8f5b9100e4dd5cad8a503a6d686efe/ETH):

<figure><img src="../../../.gitbook/assets/migrating 1.png" alt=""><figcaption></figcaption></figure>

Then, use [any of the upgrade paths](./) to upgrade the ANTv1 in your wallet to ANTv2.

Finally, you can now add liquidity to the equivalent (or new) ANTv2 pools on Uniswap. You can use [ANTv2's Uniswap analytics page](https://info.uniswap.org/token/0xa117000000f279d81a1d3cc75430faa017fa5a2e) to find ANTv2's liquidity pools.

The equivalent ANTv2/ETH pool to the original ANTv1/ETH pool is [`0x9dEF9511fEc79f83AFCBFfe4776B1D817DC775aE`](https://info.uniswap.org/pair/0x9def9511fec79f83afcbffe4776b1d817dc775ae).

## Balancer

First, withdraw any ANTv1 liquidity you've provided. For example, from the [ANTv1/WETH 80:20 pool](https://pools.balancer.exchange/#/pool/0x2cf9106faf2c5c8713035d40df655fb1b9b0f9b9/):

<figure><img src="../../../.gitbook/assets/migrating 2.png" alt=""><figcaption></figcaption></figure>

Then, use [any of the upgrade paths](https://github.com/78carla/test\_aragon-network-token/blob/master/docs/antv1/upgrade/README.md) to upgrade the ANTv1 in your wallet to ANTv2.

Finally, you can now add liquidity to the equivalent (or new) ANTv2 pools on Balancer. You can use [Balancer's ANTv2 pools page](https://pools.balancer.exchange/#/?token=0xa117000000f279d81a1d3cc75430faa017fa5a2e\&filter=1) to find ANTv2's liquidity pools.

At the moment there is an equivalent [ANTv2/WETH 80:20 pool](https://pools.balancer.exchange/#/pool/0x73eba399fbbea50852359ff8b8d0e3eba1f22500/) and a new [ANTv2/USDC 80:20 pool](https://pools.balancer.exchange/#/pool/0xde0999ee4e4bea6fecb03bf4ebef2626942ec6f5/).
