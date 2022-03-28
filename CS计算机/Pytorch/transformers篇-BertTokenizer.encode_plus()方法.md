### 一、定义

```Python
def encode_plus(
    self,
    text: Union[TextInput, PreTokenizedInput, EncodedInput],
    text_pair: Optional[Union[TextInput, PreTokenizedInput, EncodedInput]] = None,
    add_special_tokens: bool = True,
    padding: Union[bool, str, PaddingStrategy] = False,
    truncation: Union[bool, str, TruncationStrategy] = False,
    max_length: Optional[int] = None,
    stride: int = 0,
    is_split_into_words: bool = False,
    pad_to_multiple_of: Optional[int] = None,
    return_tensors: Optional[Union[str, TensorType]] = None,
    return_token_type_ids: Optional[bool] = None,
    return_attention_mask: Optional[bool] = None,
    return_overflowing_tokens: bool = False,
    return_special_tokens_mask: bool = False,
    return_offsets_mapping: bool = False,
    return_length: bool = False,
    verbose: bool = True,
    **kwargs
) -> BatchEncoding:
```

### 作用

用于将文本转化为bert的输入编码

### 参数说明

`text` 需要tokenize的文本

`max_length` 接受文本的最大长度，默认512

```Python
encoded_inputs = self.encode_plus(text,
                                  text_pair=text_pair,
                                  max_length=max_length,
                                  add_special_tokens=add_special_tokens,
                                  stride=stride,
                                  truncation_strategy=truncation_strategy,
                                  return_tensors=return_tensors,
                                  **kwargs)

return encoded_inputs["input_ids"]
```

### 常用

```Python
encoded_input = tokenizer.encode_plus(_, max_length=512, add_special_tokens=True, pad_to_max_length=True, return_tensors="pt",  truncation=True)
```

### 返回值

encode_input["input_ids"].shape=[1, max_length]or[2, max_length]

# Reference

[Transformers包tokenizer.encode()方法源码阅读笔记](https://blog.csdn.net/qq_33293040/article/details/105439750)