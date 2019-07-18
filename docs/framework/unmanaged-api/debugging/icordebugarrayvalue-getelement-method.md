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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 356f7ec9c50ce511883cbf0f5fbcb729493c92af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737571"
---
# <a name="icordebugarrayvaluegetelement-method"></a>ICorDebugArrayValue::GetElement-Methode
Ruft den Wert des angegebenen Array-Elements.  
  
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
 [in] Die Anzahl der Dimensionen dieses `ICorDebugArrayValue` Objekt.  
  
 Dieser Wert ist auch die Größe der `indices` Arrays, da seine Größe gleich der Anzahl der Dimensionen ist die `ICorDebugArrayValue` Objekt.  
  
 `indices`  
 [in] Ein Array der Indexwerte, von denen jeder eine Position innerhalb einer Dimension gibt den `ICorDebugArrayValue` Objekt.  
  
 Dieser Wert darf nicht null sein.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des angegebenen Elements darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
