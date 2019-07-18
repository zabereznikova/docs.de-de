---
title: ICorDebugValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdc889dd6b2854654bfe43b24afbe4cc19863c80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993689"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue-Schnittstelle
Stellt einen Wert in der gedebuggte Prozess. Der Wert kann es sich um einen Lesevorgang oder einen Write-Wert sein.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Diese Methode wird derzeit nicht implementiert.|  
|[GetAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Ruft die Adresse dieses `ICorDebugValue` -Objekt, das gerade gedebuggt wird.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Ruft die Größe in Bytes, davon `ICorDebugValue` Objekt.|  
|[GetType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Ruft den primitiven Typ dieses `ICorDebugValue` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Im Allgemeinen wird den Besitz eines Wertobjekts übergeben, wenn er zurückgegeben wird. Der Empfänger ist verantwortlich für das Entfernen von Verweisen aus dem Objekt, wenn sie mit dem Objekt abgeschlossen ist.  
  
 Je nachdem, in denen der Wert abgerufen wurde kann der Wert nicht gültig bleiben, nachdem der Prozess fortgesetzt wird. Also im Allgemeinen der Wert darf nicht gespeichert werden über einen Aufruf der der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Methode.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugValue3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
