---
title: ICorDebugArrayValue::GetDimensions-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: bf498a14af3dccc7278155ecfc74132c2b519ed3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698194"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a>ICorDebugArrayValue::GetDimensions-Methode

Ruft die Anzahl der Elemente in jeder Dimension dieses Arrays ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `cdim`  
 in Die Anzahl der Dimensionen dieses ICorDebugArrayValue-Objekts.  
  
 Dieser Wert ist auch die Größe des `dims` Arrays, da seine Größe gleich der Anzahl der Dimensionen des `ICorDebugArrayValue` Objekts ist.  
  
 `dims`  
 vorgenommen Ein Array von ganzen Zahlen, von denen jede die Anzahl der Elemente in einer Dimension in diesem- `ICorDebugArrayValue` Objekt angibt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
