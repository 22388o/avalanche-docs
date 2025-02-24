[avalanche](../README.md) › [API-PlatformVM-Outputs](../modules/api_platformvm_outputs.md) › [ParseableOutput](api_platformvm_outputs.parseableoutput.md)

# Class: ParseableOutput

## Hierarchy

  ↳ [StandardParseableOutput](common_output.standardparseableoutput.md)

  ↳ **ParseableOutput**

## Index

### Constructors

* [constructor](api_platformvm_outputs.parseableoutput.md#constructor)

### Properties

* [_codecID](api_platformvm_outputs.parseableoutput.md#protected-_codecid)
* [_typeID](api_platformvm_outputs.parseableoutput.md#protected-_typeid)
* [_typeName](api_platformvm_outputs.parseableoutput.md#protected-_typename)
* [output](api_platformvm_outputs.parseableoutput.md#protected-output)

### Methods

* [deserialize](api_platformvm_outputs.parseableoutput.md#deserialize)
* [fromBuffer](api_platformvm_outputs.parseableoutput.md#frombuffer)
* [getCodecID](api_platformvm_outputs.parseableoutput.md#getcodecid)
* [getOutput](api_platformvm_outputs.parseableoutput.md#getoutput)
* [getTypeID](api_platformvm_outputs.parseableoutput.md#gettypeid)
* [getTypeName](api_platformvm_outputs.parseableoutput.md#gettypename)
* [serialize](api_platformvm_outputs.parseableoutput.md#serialize)
* [toBuffer](api_platformvm_outputs.parseableoutput.md#tobuffer)
* [comparator](api_platformvm_outputs.parseableoutput.md#static-comparator)

## Constructors

###  constructor

\+ **new ParseableOutput**(`output`: [Output](common_output.output.md)): *[ParseableOutput](api_platformvm_outputs.parseableoutput.md)*

*Inherited from [ParseableOutput](api_platformvm_outputs.parseableoutput.md).[constructor](api_platformvm_outputs.parseableoutput.md#constructor)*

*Defined in [src/common/output.ts:368](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/common/output.ts#L368)*

Class representing an [ParseableOutput](api_platformvm_outputs.parseableoutput.md) for a transaction.

**Parameters:**

Name | Type | Default | Description |
------ | ------ | ------ | ------ |
`output` | [Output](common_output.output.md) | undefined | A number representing the InputID of the [ParseableOutput](api_platformvm_outputs.parseableoutput.md)  |

**Returns:** *[ParseableOutput](api_platformvm_outputs.parseableoutput.md)*

## Properties

### `Protected` _codecID

• **_codecID**: *number* = undefined

*Inherited from [SigIdx](common_signature.sigidx.md).[_codecID](common_signature.sigidx.md#protected-_codecid)*

*Defined in [src/utils/serialization.ts:40](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/utils/serialization.ts#L40)*

___

### `Protected` _typeID

• **_typeID**: *any* = undefined

*Overrides [StandardParseableOutput](common_output.standardparseableoutput.md).[_typeID](common_output.standardparseableoutput.md#protected-_typeid)*

*Defined in [src/apis/platformvm/outputs.ts:59](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/apis/platformvm/outputs.ts#L59)*

___

### `Protected` _typeName

• **_typeName**: *string* = "ParseableOutput"

*Overrides [StandardParseableOutput](common_output.standardparseableoutput.md).[_typeName](common_output.standardparseableoutput.md#protected-_typename)*

*Defined in [src/apis/platformvm/outputs.ts:58](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/apis/platformvm/outputs.ts#L58)*

___

### `Protected` output

• **output**: *[Output](common_output.output.md)*

*Inherited from [TransferableOutput](api_platformvm_outputs.transferableoutput.md).[output](api_platformvm_outputs.transferableoutput.md#protected-output)*

*Defined in [src/common/output.ts:346](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/common/output.ts#L346)*

## Methods

###  deserialize

▸ **deserialize**(`fields`: object, `encoding`: [SerializedEncoding](../modules/src_utils.md#serializedencoding)): *void*

*Overrides [StandardParseableInput](common_inputs.standardparseableinput.md).[deserialize](common_inputs.standardparseableinput.md#deserialize)*

*Defined in [src/apis/platformvm/outputs.ts:63](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/apis/platformvm/outputs.ts#L63)*

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`fields` | object | - |
`encoding` | [SerializedEncoding](../modules/src_utils.md#serializedencoding) | "hex" |

**Returns:** *void*

___

###  fromBuffer

▸ **fromBuffer**(`bytes`: Buffer, `offset`: number): *number*

*Overrides [StandardParseableOutput](common_output.standardparseableoutput.md).[fromBuffer](common_output.standardparseableoutput.md#abstract-frombuffer)*

*Defined in [src/apis/platformvm/outputs.ts:69](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/apis/platformvm/outputs.ts#L69)*

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`bytes` | Buffer | - |
`offset` | number | 0 |

**Returns:** *number*

___

###  getCodecID

▸ **getCodecID**(): *number*

*Inherited from [SigIdx](common_signature.sigidx.md).[getCodecID](common_signature.sigidx.md#getcodecid)*

*Defined in [src/utils/serialization.ts:59](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/utils/serialization.ts#L59)*

Used in serialization. Optional. TypeID is a number for the typeID of object being output.

**Returns:** *number*

___

###  getOutput

▸ **getOutput**(): *[Output](common_output.output.md)*

*Inherited from [TransferableOutput](api_platformvm_outputs.transferableoutput.md).[getOutput](api_platformvm_outputs.transferableoutput.md#getoutput)*

*Defined in [src/common/output.ts:357](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/common/output.ts#L357)*

**Returns:** *[Output](common_output.output.md)*

___

###  getTypeID

▸ **getTypeID**(): *number*

*Inherited from [SigIdx](common_signature.sigidx.md).[getTypeID](common_signature.sigidx.md#gettypeid)*

*Defined in [src/utils/serialization.ts:52](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/utils/serialization.ts#L52)*

Used in serialization. Optional. TypeID is a number for the typeID of object being output.

**Returns:** *number*

___

###  getTypeName

▸ **getTypeName**(): *string*

*Inherited from [SigIdx](common_signature.sigidx.md).[getTypeName](common_signature.sigidx.md#gettypename)*

*Defined in [src/utils/serialization.ts:45](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/utils/serialization.ts#L45)*

Used in serialization. TypeName is a string name for the type of object being output.

**Returns:** *string*

___

###  serialize

▸ **serialize**(`encoding`: [SerializedEncoding](../modules/src_utils.md#serializedencoding)): *object*

*Inherited from [ParseableOutput](api_platformvm_outputs.parseableoutput.md).[serialize](api_platformvm_outputs.parseableoutput.md#serialize)*

*Overrides [Serializable](utils_serialization.serializable.md).[serialize](utils_serialization.serializable.md#serialize)*

*Defined in [src/common/output.ts:338](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/common/output.ts#L338)*

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`encoding` | [SerializedEncoding](../modules/src_utils.md#serializedencoding) | "hex" |

**Returns:** *object*

___

###  toBuffer

▸ **toBuffer**(): *Buffer*

*Inherited from [ParseableOutput](api_platformvm_outputs.parseableoutput.md).[toBuffer](api_platformvm_outputs.parseableoutput.md#tobuffer)*

*Defined in [src/common/output.ts:362](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/common/output.ts#L362)*

**Returns:** *Buffer*

___

### `Static` comparator

▸ **comparator**(): *function*

*Inherited from [TransferableOutput](api_platformvm_outputs.transferableoutput.md).[comparator](api_platformvm_outputs.transferableoutput.md#static-comparator)*

*Defined in [src/common/output.ts:351](https://github.com/ava-labs/avalanchejs/blob/ae78dee/src/common/output.ts#L351)*

Returns a function used to sort an array of [ParseableOutput](api_platformvm_outputs.parseableoutput.md)s

**Returns:** *function*

▸ (`a`: [StandardParseableOutput](common_output.standardparseableoutput.md), `b`: [StandardParseableOutput](common_output.standardparseableoutput.md)): *1 | -1 | 0*

**Parameters:**

Name | Type |
------ | ------ |
`a` | [StandardParseableOutput](common_output.standardparseableoutput.md) |
`b` | [StandardParseableOutput](common_output.standardparseableoutput.md) |
