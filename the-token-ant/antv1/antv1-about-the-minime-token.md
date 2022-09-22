# About the MiniMe token

{% hint style="warning" %}
Some specific information about the **MiniMe token** may be useful, even when not programmatically interacting with the contract.

> **This page contains technical information.**
{% endhint %}

## Focus

* **ANTv1** is an instance of a **MiniMe token**.
* MiniMe tokens are **standard ERC20** tokens with **additional functionality**.

## Advanced functionality

### The token is easy to clone!

Anybody can create a **new clone token from a MiniMe** token with an initial distribution identical to the original token at a specified block. The address calling the `createCloneToken()` function will become the token controller and the token's default settings can be specified in the function call.

```
function createCloneToken(
    string _cloneTokenName,
    uint8 _cloneDecimalUnits,
    string _cloneTokenSymbol,
    uint _snapshotBlock,
    bool _isConstant
)
    returns (address);
```

Once the clone token is created, it acts as a completely independent token, with its own unique functionalities.

### Balance history is registered and available to be queried

All MiniMe tokens maintain a history of the balance changes that occur during each block. Two calls are introduced to read the total supply and the balance of any address at any block in the past.

```
function totalSupplyAt(uint _blockNumber) view returns (uint);

function balanceOfAt(address _holder, uint _blockNumber) view returns (uint);
```

### Optional token controller

The **controller** of the contract can **generate/destroy/transfer tokens** at its own discretion. The controller can be a regular account, but the intention is for the controller to be another contract that imposes transparent rules on the token's issuance and functionality. The token controller is not required for the MiniMe token to function, if there is no reason to generate/destroy/transfer tokens, the controller can be set to `address(0)` and this functionality will be disabled.

For example, a TokenCreation contract can be set as the controller of the MiniMe token and at the end of the token creation period, the controller can be transferred to `address(0)`, to guarantee that no new tokens will be created.

To create and destroy tokens, these two functions are introduced:

```
function generateTokens(address _holder, uint _value) onlyController;

function destroyTokens(address _holder, uint _value) onlyController;
```

### The token controller can freeze transfers

If `transfersEnabled == false`, tokens cannot be transferred directly by holders. However they can still be created, destroyed, and transferred by the controller. The controller can also toggle this flag.

```
// Allows tokens to be transferred if true or frozen if false
function enableTransfers(bool _transfersEnabled) onlyController;
```

## Applications

The cloning functionality allows for incredibly powerful functionality, effectively the ability for anyone to give extra features to the token holders without having to migrate to a new contract. Some of the applications that the MiniMe token contract can be used for are:

1. Generating a voting token that is burned when you vote.
2. Generating a discount "coupon" that is redeemed when you use it.
3. Generating a token for a "spinoff" DAO.
4. Generating a token that can be used to give explicit support to an action or a campaign, like polling.
5. Generating a token to enable the token holders to collect daily, monthly or yearly payments.
6. Generating a token to limit participation in a token sale or similar event to holders of a specific token.
7. Generating token that allows a central party complete control to transfer/generate/destroy tokens at will.
8. Lots of other applications including all the applications the standard ERC20 token can be used for.

All these applications and more are enabled by the MiniMe token contract. The most amazing part being that anyone who wants to add these features has the ability to, in a permissionless yet safe manner without affecting the parent token's intended functionality.
