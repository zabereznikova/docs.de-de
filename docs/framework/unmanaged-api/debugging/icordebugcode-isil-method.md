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
ms.openlocfilehash: 77e55c4c3644ac4bd76f5c92152f4ee86cf5fa9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125566"
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

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
