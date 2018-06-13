---
title: ICorDebugModule Schnittstelle1
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
ms.openlocfilehash: db4a980929a644d2862a382f147505644313da7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422236"
---
# <a name="icordebugmodule-interface1"></a>ICorDebugModule Schnittstelle1
Stellt ein common Language Runtime (CLR) Modul, das eine ausführbare Datei oder eine Dynamic Link Library (DLL) ist.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|Nicht implementiert.|  
|[EnableClassLoadCallbacks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|Bestimmt, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.|  
|[EnableJITDebugging-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Bestimmt, ob der Just-in-Time (JIT)-Compiler Debuginformationen für Methoden innerhalb dieses Moduls beibehält.|  
|[GetAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|Ruft die enthaltende Assembly für dieses Modul ab.|  
|[GetBaseAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|Ruft die Basisadresse des Moduls ab.|  
|[GetClassFromToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|Ruft die ICorDebugClass aus den Metadaten ab.|  
|[GetEditAndContinueSnapshot-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|Veraltet.|  
|[GetFunctionFromRVA-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|Nicht implementiert.|  
|[GetFunctionFromToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|Ruft die Funktion, die durch das Metadatentoken angegeben wird.|  
|[GetGlobalVariableValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|Ruft ein Wertobjekt für die angegebene globale Variable ab.|  
|[GetMetaDataInterface-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|Ruft einen Schnittstellenzeiger für Metadaten, der verwendet werden kann, um die Metadaten für das Modul untersuchen.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|Ruft den Dateinamen des Moduls ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|Ruft den enthaltenden Prozess für dieses Modul ab.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|Ruft die Größe des Moduls in Bytes ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|Ruft das Token für den Tabelleneintrag für dieses Modul an.|  
|[IsDynamic-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|Gibt an, ob das Modul dynamisch ist.|  
|[IsInMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
