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
ms.openlocfilehash: c573e6b768aee1e8b681dcf2e828dc24d409025b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793012"
---
# <a name="icordebugmodule-interface"></a>ICorDebugModule-Schnittstelle

Stellt ein Common Language Runtime (CLR)-Modul dar, bei dem es sich entweder um eine ausführbare Datei oder eine DLL (Dynamic Link Library) handelt.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](icordebugmodule-createbreakpoint-method.md)|Nicht implementiert.|  
|[EnableClassLoadCallbacks-Methode](icordebugmodule-enableclassloadcallbacks-method.md)|Bestimmt, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.|  
|[EnableJITDebugging-Methode](icordebugmodule-enablejitdebugging-method.md)|Bestimmt, ob der JIT-Compiler (Just-in-Time) Debuginformationen für Methoden in diesem Modul beibehält.|  
|[GetAssembly-Methode](icordebugmodule-getassembly-method.md)|Ruft die enthaltende Assembly für dieses Modul ab.|  
|[GetBaseAddress-Methode](icordebugmodule-getbaseaddress-method.md)|Ruft die Basisadresse des Moduls ab.|  
|[GetClassFromToken-Methode](icordebugmodule-getclassfromtoken-method.md)|Ruft die ICorDebugClass aus den Metadaten ab.|  
|[GetEditAndContinueSnapshot-Methode](icordebugmodule-geteditandcontinuesnapshot-method.md)|Veraltet.|  
|[GetFunctionFromRVA-Methode](icordebugmodule-getfunctionfromrva-method.md)|Nicht implementiert.|  
|[GetFunctionFromToken-Methode](icordebugmodule-getfunctionfromtoken-method.md)|Ruft die Funktion ab, die vom Metadatentoken angegeben wird.|  
|[GetGlobalVariableValue-Methode](icordebugmodule-getglobalvariablevalue-method.md)|Ruft ein Wertobjekt für die angegebene globale Variable ab.|  
|[GetMetaDataInterface-Methode](icordebugmodule-getmetadatainterface-method.md)|Ruft einen Metadatenschnittstellen Zeiger ab, der verwendet werden kann, um die Metadaten für das Modul zu überprüfen.|  
|[GetName-Methode](icordebugmodule-getname-method.md)|Ruft den Dateinamen des Moduls ab.|  
|[GetProcess-Methode](icordebugmodule-getprocess-method.md)|Ruft den enthaltenden Prozess für dieses Modul ab.|  
|[GetSize-Methode](icordebugmodule-getsize-method.md)|Ruft die Größe des Moduls in Bytes ab.|  
|[GetToken-Methode](icordebugmodule-gettoken-method.md)|Ruft das Token für den Tabelleneintrag für dieses Modul ab.|  
|[IsDynamic-Methode](icordebugmodule-isdynamic-method.md)|Gibt an, ob das Modul dynamisch ist.|  
|[IsInMemory-Methode](icordebugmodule-isinmemory-method.md)|Gibt an, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](icordebug-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
