---
title: ICorDebugValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue
helpviewer_keywords: ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01c94df1d8e6ddef0110268461a2b28f594201b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue Schnittstelle1
Stellt einen Wert im gedebuggten Prozess dar. Der Wert kann eine Lese- oder Schreibzugriff Wert sein.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Diese Methode wird derzeit nicht implementiert.|  
|[GetAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Ruft die Adresse dieses `ICorDebugValue` -Objekt, das gerade gedebuggt wird.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Ruft die Größe in Bytes dieses `ICorDebugValue` Objekt.|  
|[GetType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Ruft den primitiven Typ dieses `ICorDebugValue` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Im Allgemeinen wird den Besitz von ein Wertobjekt übergeben, wenn es zurückgegeben wird. Der Empfänger ist verantwortlich für das Entfernen eines Verweises aus dem Objekt ein, wenn er mit dem Objekt abgeschlossen ist.  
  
 Je nachdem, aus denen der Wert abgerufen wurde kann der Wert nicht gültig bleiben, nachdem der Prozess fortgesetzt wird. Daher im Allgemeinen der Wert darf nicht beibehalten über einen Aufruf der der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Methode.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
    
    
    
 [ICorDebugValue3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
