---
title: ICorDebugCode::IsIL-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a81f4a53954c559ab12e27bcf039b7b1a1804cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700793"
---
# <a name="icordebugcodeisil-method"></a>ICorDebugCode::IsIL-Methode

Ruft einen Wert ab, der angibt, ob dieser "ICorDebugCode" Code darstellt, der in der Microsoft Intermediate Language (MSIL) kompiliert wurde.

## <a name="syntax"></a>Syntax

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a>Parameter
 `pbIL`  
 [out] `true`, wenn dieser `ICorDebugCode` Code darstellt, der in MSIL kompiliert wurde. Andernfalls `false`.

## <a name="requirements"></a>Anforderungen

 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  

 **Header:** Cordebug. idl, Cordebug. h  

 **Fern** CorGuids.lib  

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
 
