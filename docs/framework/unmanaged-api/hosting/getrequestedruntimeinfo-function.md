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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178155"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo-Funktion
Ruft Versions- und Verzeichnisinformationen über die von einer Anwendung angeforderte Common Language Runtime (CLR) ab.  
  
 Diese Funktion ist in .NET Framework 4 veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 [in] Eine Zeichenfolge, die die Versionsnummer der Laufzeit angibt.  
  
 `pConfigurationFile`  
 [in] Der Name der Konfigurationsdatei, `pExe`die mit verknüpft ist.  
  
 `startupFlags`  
 [in] Mindestens einer der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) STARTUP_FLAGS-Enumerationswerte.  
  
 `runtimeInfoFlags`  
 [in] Mindestens einer der [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) RUNTIME_INFO_FLAGS-Enumerationswerte.  
  
 `pDirectory`  
 [out] Ein Puffer, der den Verzeichnispfad zur Laufzeit nach erfolgreichem Abschluss enthält.  
  
 `dwDirectory`  
 [in] Die Länge des Verzeichnispuffers.  
  
 `dwDirectoryLength`  
 [out] Ein Zeiger auf die Länge der Verzeichnispfadzeichenfolge.  
  
 `pVersion`  
 [out] Ein Puffer, der die Versionsnummer der Laufzeit nach erfolgreichem Abschluss enthält.  
  
 `cchBuffer`  
 [in] Die Länge des Versionszeichenfolgenpuffers.  
  
 `dwlength`  
 [out] Ein Zeiger auf die Länge der Versionszeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt zusätzlich zu den folgenden Werten Com-Fehlercodes (Standard Component Object Model, COM) zurück, wie in WinError.h definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|ERROR_INSUFFICIENT_BUFFER|Der Verzeichnispuffer ist nicht groß genug, um den Verzeichnispfad zu speichern.<br /><br /> - oder -<br /><br /> Der Versionspuffer ist nicht groß genug, um die Versionszeichenfolge zu speichern.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die `GetRequestedRuntimeInfo` Methode gibt Laufzeitinformationen über die in den Prozess geladene Version zurück, die nicht unbedingt die neueste Version ist, die auf dem Computer installiert ist.  
  
 In .NET Framework Version 2.0 können Sie Informationen über die `GetRequestedRuntimeInfo` neueste installierte Version abrufen, indem Sie die Methode wie folgt verwenden:  
  
- Geben `pExe`Sie `pwszVersion`die `pConfigurationFile` , und die Parameter als null an.  
  
- Geben Sie das `RUNTIME_INFO_FLAGS` RUNTIME_INFO_UPGRADE_VERSION-Flag in `runtimeInfoFlags` den Enumerationen für den Parameter an.  
  
 Die `GetRequestedRuntimeInfo` Methode gibt unter den folgenden Umständen nicht die neueste CLR-Version zurück:  
  
- Eine Anwendungskonfigurationsdatei, die das Laden einer bestimmten CLR-Version angibt, ist vorhanden. Beachten Sie, dass .NET Framework die Konfigurationsdatei auch `pConfigurationFile` dann verwendet, wenn Sie null für den Parameter angeben.  
  
- Die [CorBindToRuntimeEx-Methode](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) wurde aufgerufen, die eine frühere CLR-Version angibt.  
  
- Eine Anwendung, die für eine frühere CLR-Version kompiliert wurde, wird derzeit ausgeführt.  
  
 Für `runtimeInfoFlags` den Parameter können Sie jeweils nur eine `RUNTIME_INFO_FLAGS` der Architekturkonstanten der Enumeration angeben:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetRequestedRuntimeVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
