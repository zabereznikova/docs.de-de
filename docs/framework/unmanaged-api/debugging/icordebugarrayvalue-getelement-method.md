---
title: ICorDebugArrayValue::GetElement-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: 7a52e61f41bd1d7f68523dd16f70010ffbba401e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895035"
---
# <a name="icordebugarrayvaluegetelement-method"></a>ICorDebugArrayValue::GetElement-Methode
Ruft den Wert des angegebenen Array Elements ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cdim`  
 in Die Anzahl der Dimensionen dieses `ICorDebugArrayValue` Objekts.  
  
 Dieser Wert ist auch die Größe des `indices` Arrays, da seine Größe gleich der Anzahl der Dimensionen des `ICorDebugArrayValue` Objekts ist.  
  
 `indices`  
 in Ein Array von Indexwerten, von denen jedes eine Position innerhalb einer Dimension des- `ICorDebugArrayValue` Objekts angibt.  
  
 Dieser Wert darf nicht NULL sein.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den Wert des angegebenen Elements darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
