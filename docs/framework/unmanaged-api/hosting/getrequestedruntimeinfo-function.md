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
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136323"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo-Funktion
Ruft Informationen zur Version und zum Verzeichnis der von einer Anwendung angeforderten Common Language Runtime (CLR) ab.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
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
 in Der Name der Anwendung.  
  
 `pwszVersion`  
 in Eine Zeichenfolge, die die Versionsnummer der Laufzeit angibt.  
  
 `pConfigurationFile`  
 in Der Name der Konfigurationsdatei, die `pExe`zugeordnet ist.  
  
 `startupFlags`  
 in Mindestens ein [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) -Enumerationswert.  
  
 `runtimeInfoFlags`  
 in Mindestens ein [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) -Enumerationswert.  
  
 `pDirectory`  
 vorgenommen Ein Puffer, der nach erfolgreichem Abschluss den Verzeichnispfad zur Laufzeit enthält.  
  
 `dwDirectory`  
 in Die Länge des Verzeichnis Puffers.  
  
 `dwDirectoryLength`  
 vorgenommen Ein Zeiger auf die Länge der Verzeichnispfad Zeichenfolge.  
  
 `pVersion`  
 vorgenommen Ein Puffer, der die Versionsnummer der Laufzeit nach erfolgreichem Abschluss enthält.  
  
 `cchBuffer`  
 in Die Länge des Versions Zeichen folgen Puffers.  
  
 `dwlength`  
 vorgenommen Ein Zeiger auf die Länge der Versions Zeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|ERROR_INSUFFICIENT_BUFFER|Der Verzeichnis Puffer ist nicht groß genug zum Speichern des Verzeichnis Pfads.<br /><br /> - oder -<br /><br /> Der Versions Puffer ist nicht groß genug, um die Versions Zeichenfolge zu speichern.|  
  
## <a name="remarks"></a>Hinweise  
 Die `GetRequestedRuntimeInfo`-Methode gibt Laufzeitinformationen über die Version zurück, die in den Prozess geladen wurde. Dies ist nicht notwendigerweise die neueste Version, die auf dem Computer installiert ist.  
  
 In der .NET Framework Version 2,0 können Sie Informationen zur neuesten installierten Version erhalten, indem Sie die `GetRequestedRuntimeInfo`-Methode wie folgt verwenden:  
  
- Geben Sie die Parameter `pExe`, `pwszVersion`und `pConfigurationFile` als NULL an.  
  
- Geben Sie das RUNTIME_INFO_UPGRADE_VERSION-Flag in den `RUNTIME_INFO_FLAGS` Enumerationen für den `runtimeInfoFlags`-Parameter an.  
  
 Die `GetRequestedRuntimeInfo`-Methode gibt in den folgenden Situationen nicht die neueste CLR-Version zurück:  
  
- Es ist eine Anwendungs Konfigurationsdatei vorhanden, die das Laden einer bestimmten CLR-Version angibt. Beachten Sie, dass die .NET Framework die Konfigurationsdatei auch dann verwendet, wenn Sie für den Parameter `pConfigurationFile` NULL angeben.  
  
- Die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) -Methode wurde aufgerufen, um eine frühere CLR-Version anzugeben.  
  
- Eine Anwendung, die für eine frühere CLR-Version kompiliert wurde, wird zurzeit ausgeführt.  
  
 Für den `runtimeInfoFlags`-Parameter können Sie jeweils nur eine der Architektur Konstanten der `RUNTIME_INFO_FLAGS` Enumeration angeben:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetRequestedRuntimeVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
