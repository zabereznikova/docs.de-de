---
title: CreateDebuggingInterfaceFromVersion-Funktion
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
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b3f269f5b1758481995d6064e7137e62bff4a868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion-Funktion
Erstellt ein [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.  
  
 Diese Funktion ist veraltet, in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Um eine Schnittstelle für die common Language Runtime (CLR) 2.0 zu erhalten, verwenden Sie stattdessen die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) Methode, und geben Sie die Klassen-ID CLSID_CLRDebuggingLegacy und der Schnittstellenbezeichner IID_ICorDebug. Rufen Sie eine Schnittstelle für CLR 4 oder höher Aufrufen der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) Funktion, und geben Sie die Klassen-ID CLSID_CLRDebugging und der Schnittstellenbezeichner IID_ICLRDebugging.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `iDebuggerVersion`  
 [in] Die Version des `ICorDebug` , die vom Debugger erwartet wird. Finden Sie unter der [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) Enumeration für gültige Werte.  
  
 `szDebuggeeVersion`  
 [in] Version der common Language Runtime die Anwendung oder den Prozess zu debuggende zugeordnet. Finden Sie unter der [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) oder [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) -Methode Informationen zum Abrufen dieses Werts.  
  
 `ppCordb`  
 [out] Der Speicherort, empfängt einen Zeiger auf, die `ICorDebug` Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die standard-COM-Fehlercodes zurück, wie in der Datei "WinError.h" zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szDebuggeeVersion`oder `ppCordb` ist Null, oder die Version Zeichenfolge ist falsch.|  
  
## <a name="remarks"></a>Hinweise  
 Die `szDebuggeeVersion` aufgeführte Parameter wird die entsprechende Version von "mscordbi.dll".  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
