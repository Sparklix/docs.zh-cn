---
title: CoUninitializeEE 函数
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616458"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE 函数
`CoUninitializeEE`已过时，不提供任何功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>备注  
 不能从进程中卸载公共语言运行时的执行引擎。 若要关闭执行引擎，请调用[CorExitProcess](corexitprocess-function.md)。  
  
## <a name="see-also"></a>另请参阅

- [CoInitializeEE 函数](coinitializeee-function.md)
- [元数据全局静态函数](../metadata/metadata-global-static-functions.md)
