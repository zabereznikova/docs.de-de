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
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176447"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion-Funktion
Erstellt ein [ICorDebug-Objekt](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) basierend auf den angegebenen Versionsinformationen.  
  
 Diese Funktion ist im .NET Framework 4 veraltet. Verwenden Sie stattdessen die [ICLRRuntimeInfo::GetInterface-Methode,](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) um eine Schnittstelle für die Common Language Runtime (CLR) 2.0 abrufe, und geben Sie den Klassenbezeichner CLSID_CLRDebuggingLegacy und den Schnittstellenbezeichner IID_ICorDebug an. Um eine Schnittstelle für CLR 4 oder höher abzurufen, rufen Sie die [CLRCreateInstance-Funktion](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) auf und geben Sie den Klassenbezeichner CLSID_CLRDebugging und den Schnittstellenbezeichner IID_ICLRDebugging an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `iDebuggerVersion`  
 [in] Die Version `ICorDebug` davon wird vom Debugger erwartet. Siehe [CorDebugInterfaceVersion-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) für gültige Werte.  
  
 `szDebuggeeVersion`  
 [in] Die Common Language-Laufzeitversion, die der zu debuggenden Anwendung oder dem zu debuggenden Prozess zugeordnet ist. Informationen zum Abrufen dieses Werts finden Sie in der [GetVersionFromProcess-](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) oder [GetRequestedRuntimeVersion-Methode.](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
 `ppCordb`  
 [out] Die Position, die einen `ICorDebug` Zeiger auf das Objekt empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt zusätzlich zu den folgenden Werten Standard-COM-Fehlercodes zurück, wie in der Datei WinError.h definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szDebuggeeVersion`oder `ppCordb` null ist, oder die Versionszeichenfolge ist falsch.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der `szDebuggeeVersion` Parameter wird der entsprechenden Version von MSCorDbi.dll zugeordnet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
