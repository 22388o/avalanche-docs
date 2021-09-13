[avalanche](../README.md) › [src/utils](../modules/src_utils.md) › [PrivateKeyError](src_utils.privatekeyerror.md)

# Class: PrivateKeyError

## Hierarchy

  ↳ [AvalancheError](src_utils.avalancheerror.md)

  ↳ **PrivateKeyError**

## Index

### Constructors

* [constructor](src_utils.privatekeyerror.md#constructor)

### Properties

* [errorCode](src_utils.privatekeyerror.md#errorcode)
* [message](src_utils.privatekeyerror.md#message)
* [name](src_utils.privatekeyerror.md#name)
* [stack](src_utils.privatekeyerror.md#optional-stack)

### Methods

* [getCode](src_utils.privatekeyerror.md#getcode)

## Constructors

###  constructor

\+ **new PrivateKeyError**(`m`: string): *[PrivateKeyError](src_utils.privatekeyerror.md)*

*Overrides [AvalancheError](src_utils.avalancheerror.md).[constructor](src_utils.avalancheerror.md#constructor)*

*Defined in [src/utils/errors.ts:280](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/utils/errors.ts#L280)*

**Parameters:**

Name | Type |
------ | ------ |
`m` | string |

**Returns:** *[PrivateKeyError](src_utils.privatekeyerror.md)*

## Properties

###  errorCode

• **errorCode**: *string*

*Inherited from [AvalancheError](src_utils.avalancheerror.md).[errorCode](src_utils.avalancheerror.md#errorcode)*

*Defined in [src/utils/errors.ts:44](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/utils/errors.ts#L44)*

___

###  message

• **message**: *string*

*Inherited from [AvalancheError](src_utils.avalancheerror.md).[message](src_utils.avalancheerror.md#message)*

Defined in node_modules/typescript/lib/lib.es5.d.ts:974

___

###  name

• **name**: *string*

*Inherited from [AvalancheError](src_utils.avalancheerror.md).[name](src_utils.avalancheerror.md#name)*

Defined in node_modules/typescript/lib/lib.es5.d.ts:973

___

### `Optional` stack

• **stack**? : *string*

*Inherited from [AvalancheError](src_utils.avalancheerror.md).[stack](src_utils.avalancheerror.md#optional-stack)*

Defined in node_modules/typescript/lib/lib.es5.d.ts:975

## Methods

###  getCode

▸ **getCode**(): *string*

*Inherited from [AvalancheError](src_utils.avalancheerror.md).[getCode](src_utils.avalancheerror.md#getcode)*

*Defined in [src/utils/errors.ts:51](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/utils/errors.ts#L51)*

**Returns:** *string*
