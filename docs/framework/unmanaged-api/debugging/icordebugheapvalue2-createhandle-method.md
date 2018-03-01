---
title: ICorDebugHeapValue2::CreateHandle-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eeef3215c3740cdaa7d1b78b73fde9e76d7b40c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
