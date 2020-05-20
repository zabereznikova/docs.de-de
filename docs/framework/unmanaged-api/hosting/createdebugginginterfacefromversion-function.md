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
ms.openlocfilehash: 0e1395229b67c4054df62935375a4136edf63078
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616488"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion-Funktion
Erstellt ein [ICorDebug](../debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.  
  
 Diese Funktion ist in der .NET Framework 4 veraltet. Verwenden Sie stattdessen die [iclrruntimeingefo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode, und geben Sie den Klassen Bezeichner CLSID_CLRDebuggingLegacy und den Schnittstellen Bezeichner IID_ICorDebug an, um eine Schnittstelle für die Common Language Runtime (CLR) 2,0 abzurufen. Um eine Schnittstelle für CLR 4 oder höher abzurufen, müssen Sie die [clrkreateinstance](clrcreateinstance-function.md) -Funktion aufrufen und die Klassen-ID CLSID_CLRDebugging und den Schnittstellen Bezeichner IID_ICLRDebugging angeben.  
  
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
 in Die Version von `ICorDebug` , die vom Debugger erwartet wird. Gültige Werte finden Sie in der [Cordebug](../debugging/cordebuginterfaceversion-enumeration.md) -Enumeration.  
  
 `szDebuggeeVersion`  
 in Die Common Language Runtime Version, die der zu debuggenden Anwendung oder dem Prozess zugeordnet ist. Informationen zum Abrufen dieses Werts finden Sie in der [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) -Methode oder der [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) -Methode.  
  
 `ppCordb`  
 vorgenommen Der Speicherort, der einen Zeiger auf das- `ICorDebug` Objekt empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Standard-COM-Fehlercodes zurück, wie in der Datei "Winerror. h" zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szDebuggeeVersion`oder `ppCordb` ist NULL, oder die Versions Zeichenfolge ist falsch.|  
  
## <a name="remarks"></a>Hinweise  
 Der- `szDebuggeeVersion` Parameter wird der entsprechenden Version von mscordbi. dll zugeordnet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
