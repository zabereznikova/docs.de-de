---
title: ICorDebugReferenceValue::SetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
ms.openlocfilehash: 892471e7b35b4f4093df3f86d4777947b6e484e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378305"
---
# <a name="icordebugreferencevaluesetvalue-method"></a>ICorDebugReferenceValue::SetValue-Methode
Legt die angegebene Speicheradresse fest. Das heißt, diese Methode legt diese ICorDebugReferenceValue so fest, dass Sie auf ein Objekt verweist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `value`  
 in Ein- `CORDB_ADDRESS` Wert, der die Adresse des-Objekts angibt, auf das dieser `ICorDebugReferenceValue` verweist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
