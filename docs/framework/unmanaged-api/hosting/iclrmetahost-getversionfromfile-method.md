---
title: ICLRMetaHost::GetVersionFromFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
ms.openlocfilehash: 40efc256dde13d645d43f50bb574d73b5668919c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703739"
---
# <a name="iclrmetahostgetversionfromfile-method"></a>ICLRMetaHost::GetVersionFromFile-Methode
Ruft die ursprüngliche .NET Framework Kompilierungs Version einer Assembly ab (gespeichert in den Metadaten), wenn Ihr Dateipfad angegeben ist. Diese Methode löst die [GetFileVersion](getfileversion-function.md) -Funktion aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzFilePath`  
 in Der vollständige assemblydateipfad.  
  
 `pwzbuffer`  
 vorgenommen Die in den Metadaten gespeicherte .NET Framework Kompilierungs Version im Format "v*A*. *B*[.* X*] ". *A*, *B*und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen. Die Länge dieser Zeichenfolge ist auf MAX_PATH beschränkt.  
  
> [!NOTE]
> Diese Ausgabe entspricht dem Verzeichnisnamen für die .NET Framework Version, wie Sie unter "c:\WINDOWS\Microsoft.NET\Framework" angezeigt wird.  
  
 Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *X*", wobei *x* von der installierten Buildnummer abhängig ist. Beachten Sie, dass das Präfix "v" erforderlich ist.  
  
 `pcchBuffer`  
 [in, out] Die Größe von `pwzbuffer` , um Pufferüberläufe zu vermeiden.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pwzbuffer` oder `pcchBuffer` ist NULL.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Der Puffer ist zu klein.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](iclrmetahost-interface.md)
- [Hosting](index.md)
