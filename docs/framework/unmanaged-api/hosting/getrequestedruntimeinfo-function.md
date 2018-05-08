---
title: GetRequestedRuntimeInfo-Funktion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f37be8e3d2e92147e9f13954ab64396062ade2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo-Funktion
Ruft Version und Verzeichnisinformationen über die common Language Runtime (CLR), das von einer Anwendung angefordert ab.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pExe`  
 [in] Der Name der Anwendung.  
  
 `pwszVersion`  
 [in] Eine Zeichenfolge, die Versionsnummer der Laufzeit angeben.  
  
 `pConfigurationFile`  
 [in] Der Name der Konfigurationsdatei, die mit zugeordnetem `pExe`.  
  
 `startupFlags`  
 [in] Ein oder mehrere der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Enumerationswerte.  
  
 `runtimeInfoFlags`  
 [in] Ein oder mehrere der [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) Enumerationswerte.  
  
 `pDirectory`  
 [out] Ein Puffer, der den Verzeichnispfad für die Common Language Runtime nach dem erfolgreichen Abschluss enthält.  
  
 `dwDirectory`  
 [in] Die Länge des Verzeichnispuffers.  
  
 `dwDirectoryLength`  
 [out] Ein Zeiger auf die Länge der Zeichenfolge für den Verzeichnispfad.  
  
 `pVersion`  
 [out] Ein Puffer, der die Versionsnummer der Common Language Runtime nach dem erfolgreichen Abschluss enthält.  
  
 `cchBuffer`  
 [in] Die Länge des Puffers für die Versionszeichenfolge.  
  
 `dwlength`  
 [out] Ein Zeiger auf die Länge der Versionszeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|ERROR_INSUFFICIENT_BUFFER|Der Verzeichnis-Puffer ist nicht groß genug ist, um den Verzeichnispfad zu speichern.<br /><br /> - oder -<br /><br /> Die Version Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.|  
  
## <a name="remarks"></a>Hinweise  
 Die `GetRequestedRuntimeInfo` Methodenrückgabe Laufzeitinformationen über die Version geladenen des Prozesses, der nicht unbedingt die neueste Version auf dem Computer installiert ist.  
  
 In .NET Framework, Version 2.0, können Sie Informationen über die neueste installierte Version abrufen, mithilfe der `GetRequestedRuntimeInfo` -Methode wie folgt:  
  
-   Geben Sie die `pExe`, `pwszVersion`, und `pConfigurationFile` Parameter als Null.  
  
-   Geben Sie das RUNTIME_INFO_UPGRADE_VERSION-Flag in der `RUNTIME_INFO_FLAGS` Enumerationen für die `runtimeInfoFlags` Parameter.  
  
 Die `GetRequestedRuntimeInfo` Methode gibt nicht die neueste Version der CLR zurück, in den folgenden Situationen:  
  
-   Eine Anwendungskonfigurationsdatei, die angibt, das Laden einer bestimmten CLR-Version vorhanden ist. Beachten Sie, dass .NET Framework die Konfigurationsdatei verwenden wird, auch wenn Sie null für den `pConfigurationFile` Parameter.  
  
-   Die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Methode wurde aufgerufen, die eine frühere Version der CLR angibt.  
  
-   Eine Anwendung, die für eine frühere Version der CLR kompiliert wurde, wird derzeit ausgeführt.  
  
 Für die `runtimeInfoFlags` Parameter, Sie können Geben Sie nur eine der Architekturkonstanten von der `RUNTIME_INFO_FLAGS` Enumeration zu einem Zeitpunkt:  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [GetRequestedRuntimeVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [GetVersionFromProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
