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
ms.openlocfilehash: 1290aa864a3f65e549bc26173dcd23648b8dee90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61627985"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo-Funktion
Ruft Version und Verzeichnisinformationen Informationen über die common Language Runtime (CLR), das von einer Anwendung angefordert.  
  
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
  
## <a name="parameters"></a>Parameter  
 `pExe`  
 [in] Der Name der Anwendung.  
  
 `pwszVersion`  
 [in] Eine Zeichenfolge, die die Versionsnummer der Laufzeit angeben.  
  
 `pConfigurationFile`  
 [in] Der Name der Konfigurationsdatei, die zugeordnet wird `pExe`.  
  
 `startupFlags`  
 [in] Mindestens eines der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) -Enumerationswerte fest.  
  
 `runtimeInfoFlags`  
 [in] Mindestens eines der [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) -Enumerationswerte fest.  
  
 `pDirectory`  
 [out] Ein Puffer, der den Verzeichnispfad für die Laufzeit nach dem erfolgreichen Abschluss enthält.  
  
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
 Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|ERROR_INSUFFICIENT_BUFFER|Der Directory-Puffer ist nicht groß genug ist, um den Verzeichnispfad zu speichern.<br /><br /> - oder -<br /><br /> Die Version-Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.|  
  
## <a name="remarks"></a>Hinweise  
 Die `GetRequestedRuntimeInfo` Methodenrückgabe Laufzeitinformationen über die Version geladen, die in den Prozess, der nicht unbedingt die neueste Version auf dem Computer installiert ist.  
  
 In .NET Framework, Version 2.0, erhalten Sie Informationen über die neueste installierte Version mithilfe der `GetRequestedRuntimeInfo` -Methode wie folgt:  
  
- Geben Sie die `pExe`, `pwszVersion`, und `pConfigurationFile` Parameter als Null.  
  
- Geben Sie das Flag RUNTIME_INFO_UPGRADE_VERSION in die `RUNTIME_INFO_FLAGS` Enumerationen für die `runtimeInfoFlags` Parameter.  
  
 Die `GetRequestedRuntimeInfo` Methode nicht die neueste Version der CLR in den folgenden Situationen zurückgegeben:  
  
- Die Konfigurationsdatei einer Anwendung, die angibt, laden eine bestimmte CLR-Version vorhanden ist. Beachten Sie, dass .NET Framework die Konfigurationsdatei verwendet wird, auch wenn Sie null für angeben der `pConfigurationFile` Parameter.  
  
- Die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Methode wurde aufgerufen, die eine frühere Version der CLR angibt.  
  
- Eine Anwendung, die für eine frühere Version der CLR kompiliert wurde, wird derzeit ausgeführt.  
  
 Für die `runtimeInfoFlags` -Parameters, können Sie angeben nur eine der Architekturkonstanten der `RUNTIME_INFO_FLAGS` Enumeration zu einem Zeitpunkt:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetRequestedRuntimeVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
