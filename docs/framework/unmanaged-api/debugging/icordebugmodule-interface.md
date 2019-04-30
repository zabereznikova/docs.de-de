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
ms.openlocfilehash: 257011562a9ea687ef70b842c6d47219283e158e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988028"
---
# <a name="icordebugmodule-interface"></a>ICorDebugModule-Schnittstelle

Stellt ein common Language Runtime (CLR) Modul, das entweder eine ausführbare Datei oder eine Dynamic Link Library (DLL) ist.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|Nicht implementiert.|  
|[EnableClassLoadCallbacks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|Bestimmt, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.|  
|[EnableJITDebugging-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Bestimmt, ob der just-in-Time (JIT)-Compiler Debuginformationen für Methoden in diesem Modul werden beibehalten.|  
|[GetAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|Ruft die übergeordnete Assembly für dieses Modul ab.|  
|[GetBaseAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|Ruft die Basisadresse des Moduls ab.|  
|[GetClassFromToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|Ruft die ICorDebugClass aus den Metadaten ab.|  
|[GetEditAndContinueSnapshot-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|Veraltet.|  
|[GetFunctionFromRVA-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|Nicht implementiert.|  
|[GetFunctionFromToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|Ruft die Funktion, die durch das Metadatentoken angegeben wird.|  
|[GetGlobalVariableValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|Ruft ein Wertobjekt für die angegebene globale Variable ab.|  
|[GetMetaDataInterface-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|Ruft ab einen Metadaten-Schnittstellenzeiger, der verwendet werden kann, um die Metadaten für das Modul zu untersuchen.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|Ruft den Dateinamen des Moduls ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|Ruft die enthaltende Prozess für dieses Modul ab.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|Ruft die Größe des Moduls in Bytes ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|Ruft das Token für den Tabelleneintrag für dieses Modul ab.|  
|[IsDynamic-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|Gibt an, ob das Modul dynamisch ist.|  
|[IsInMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
