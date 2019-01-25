---
title: CreateDebuggingInterfaceFromVersion-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bfba74137bab6dfe90626b5600193494df795d77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695581"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion-Funktion
Erstellt eine [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.  
  
 Diese Funktion ist veraltet, in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Um eine Schnittstelle für die common Language Runtime (CLR) 2.0 zu erhalten, verwenden Sie stattdessen die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) Methode, und geben Sie die Klassen-ID CLSID_CLRDebuggingLegacy und der schnittstellenkennung IID_ICorDebug. Erhalten eine Schnittstelle für die CLR 4 oder höher, rufen Sie die [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) Funktion, und geben Sie die Klassen-ID CLSID_CLRDebugging und der schnittstellenkennung IID_ICLRDebugging.  
  
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
 [in] Die Version des `ICorDebug` , die vom Debugger erwartet wird. Finden Sie unter den [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) -Enumeration für gültige Werte.  
  
 `szDebuggeeVersion`  
 [in] Version der common Language Runtime die Anwendung oder den Prozess zu debuggende zugeordnet. Finden Sie unter den [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) oder [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) Methode für die Informationen zum Abrufen dieses Werts.  
  
 `ppCordb`  
 [out] Der Speicherort, der einen Zeiger auf empfängt die `ICorDebug` Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die standard-COM-Fehlercodes zurück, wie in der Datei "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szDebuggeeVersion` oder `ppCordb` ist Null, oder die Version Zeichenfolge ist falsch.|  
  
## <a name="remarks"></a>Hinweise  
 Die `szDebuggeeVersion` Parameter ist die entsprechende Version von "mscordbi.dll" zugeordnet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
