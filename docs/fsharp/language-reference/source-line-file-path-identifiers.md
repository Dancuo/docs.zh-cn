---
title: "源代码行标识符、文件标识符和路径标识符 (F#)"
description: "了解如何使用内置 F # 标识符的值使你能够访问源行号、 目录和在代码中的文件名称。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="source-line-file-and-path-identifiers"></a>源代码行标识符、文件标识符和路径标识符

标识符`__LINE__`，`__SOURCE_DIRECTORY__`和`__SOURCE_FILE__`是内置值，它们使你能够访问你的代码中的源行号、 目录和文件名称。


## <a name="syntax"></a>语法

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>备注
其中每个值具有类型`string`。

下表总结了源行、 文件和 F # 中可用的路径标识符。 这些标识符不是预处理器宏;它们是由编译器识别的内置值。

|预定义的标识符|描述|
|---------------------|-----------|
|`__LINE__`|计算结果为当前行号，考虑`#line`指令。|
|`__SOURCE_DIRECTORY__`|计算结果为当前的完整路径的源目录中，考虑`#line`指令。|
|`__SOURCE_FILE__`|计算结果为当前的源文件的名称，其路径中，考虑`#line`指令。|
有关详细信息`#line`指令，请参阅[编译器指令](compiler-directives.md)。

## <a name="example"></a>示例

下面的代码示例演示如何将这些值。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

输出：

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>另请参阅
[编译器指令](compiler-directives.md)

[F# 语言参考](index.md)
