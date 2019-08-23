---
title: ICorDebugModule-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dce4f5859568c1288610e171286a5919dc8b19b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962430"
---
# <a name="icordebugmodule-interface"></a>ICorDebugModule-Schnittstelle

Stellt ein Common Language Runtime (CLR)-Modul dar, bei dem es sich entweder um eine ausführbare Datei oder eine DLL (Dynamic Link Library) handelt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|Nicht implementiert.|  
|[EnableClassLoadCallbacks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|Bestimmt, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.|  
|[EnableJITDebugging-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Bestimmt, ob der JIT-Compiler (Just-in-Time) Debuginformationen für Methoden in diesem Modul beibehält.|  
|[GetAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|Ruft die enthaltende Assembly für dieses Modul ab.|  
|[GetBaseAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|Ruft die Basisadresse des Moduls ab.|  
|[GetClassFromToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|Ruft die ICorDebugClass aus den Metadaten ab.|  
|[GetEditAndContinueSnapshot-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|Veraltet.|  
|[GetFunctionFromRVA-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|Nicht implementiert.|  
|[GetFunctionFromToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|Ruft die Funktion ab, die vom Metadatentoken angegeben wird.|  
|[GetGlobalVariableValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|Ruft ein Wertobjekt für die angegebene globale Variable ab.|  
|[GetMetaDataInterface-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|Ruft einen Metadatenschnittstellen Zeiger ab, der verwendet werden kann, um die Metadaten für das Modul zu überprüfen.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|Ruft den Dateinamen des Moduls ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|Ruft den enthaltenden Prozess für dieses Modul ab.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|Ruft die Größe des Moduls in Bytes ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|Ruft das Token für den Tabelleneintrag für dieses Modul ab.|  
|[IsDynamic-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|Gibt an, ob das Modul dynamisch ist.|  
|[IsInMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
