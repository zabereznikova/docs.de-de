---
title: ICorDebugRegisterSet-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 940810288b72be0d4dfc5366176663c22c369ebb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712377"
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet-Schnittstelle

Stellt den Satz der Register dar, die auf dem Computer verfügbar sind, der derzeit Code ausführt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetRegisters-Methode](icordebugregisterset-getregisters-method.md)|Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.|  
|[GetRegistersAvailable-Methode](icordebugregisterset-getregistersavailable-method.md)|Ruft eine Bitmaske ab, die angibt, welche Register in diesem `ICorDebugRegisterSet` aktuell verfügbar sind.|  
|[GetThreadContext-Methode](icordebugregisterset-getthreadcontext-method.md)|Ruft den Kontext des aktuellen Threads ab.|  
|[SetRegisters-Methode](icordebugregisterset-setregisters-method.md)|Nicht implementiert für die .NET Framework Version 2,0.|  
|[SetThreadContext-Methode](icordebugregisterset-setthreadcontext-method.md)|Nicht implementiert für den .NET Framework 2,0.|  
  
## <a name="remarks"></a>Hinweise  

 Die `ICorDebugRegisterSet` -Schnittstelle unterstützt nur 32-Bit-Register. Verwenden Sie die [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) -Schnittstelle auf Plattformen wie IA-64, die zusätzliche Register erfordern.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
