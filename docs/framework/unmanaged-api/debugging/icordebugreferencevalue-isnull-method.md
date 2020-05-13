---
title: ICorDebugReferenceValue::IsNull-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: e8b778c0880040f5ffd639a445fd5663ce493219
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379088"
---
# <a name="icordebugreferencevalueisnull-method"></a>ICorDebugReferenceValue::IsNull-Methode
Ruft einen Wert ab, der angibt, ob dieser ICorDebugReferenceValue ein NULL-Wert ist. in diesem Fall verweist der `ICorDebugReferenceValue` nicht auf ein Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbNull`  
 vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn dieses `ICorDebugReferenceValue` Objekt NULL ist, andernfalls `pbNull` ist `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
