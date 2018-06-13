---
title: ICorDebugHeapValue2::CreateHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c69d1f83a4591df4d2dcb7fb9724fa582ea28387
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413578"
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle-Methode
Erstellt ein Handle des angegebenen Typs für den Heapwert, der von diesem ICorDebugHeapValue2-Objekt dargestellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `type`  
 [in] Der Wert CorDebugHandleType-Enumeration, die den Typ des zu erstellenden Handle angibt.  
  
 `ppHandle`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugHandleValue-Objekts, das das neue Handle für diesen Heapwert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Das Handle erstellt werden, in der Anwendungsdomäne, die den Heapwert zugeordnet ist, und wird ungültig, wenn die Anwendungsdomäne entladen wird.  
  
 Mehrere Aufrufe dieser Funktion für den gleichen Heapwert werden mehrere Handles erstellt. Da Handles auf die Leistung des Garbage Collectors auswirken, sollte der Debugger selbst auf eine relativ kleine Anzahl von Handles (ungefähr 256) einschränken, die gleichzeitig aktiv sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
