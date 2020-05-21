---
title: ICLRRuntimeInfo::GetVersionString-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: ccf48b6aea25bd602b55727c2e5958811702f6bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762577"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>ICLRRuntimeInfo::GetVersionString-Methode
Ruft die einer bestimmten [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zugeordneten Common Language Runtime (CLR) ab.  
  
 Diese Methode ersetzt die folgenden Funktionen:  
  
- [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)  
  
- [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzBuffer`  
 vorgenommen Die .NET Framework Kompilierungs Version im Format "v*A*. *B*[.* X*] ". *A*, *B*und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen. *X* ist optional. Wenn *X* nicht vorhanden ist, gibt es keinen nachfolgenden Zeitraum.  
  
> [!NOTE]
> Dieser Parameter muss dem Verzeichnisnamen für die .NET Framework Version entsprechen, wie er unter "c:\WINDOWS\Microsoft.NET\Framework" angezeigt wird.  
  
 Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *x*", wobei *x* von der installierten Buildnummer abhängig ist. Beachten Sie, dass das Präfix "v" obligatorisch ist.  
  
 `pchBuffer`  
 [in, out] Gibt die Größe von `pwzBuffer` an, um Pufferüberläufe zu vermeiden. Wenn `pwzBuffer` ist `null` , wird `pchBuffer` die erforderliche Größe von zurückgegeben `pwzBuffer` , um die vorab Zuordnung zuzulassen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pwzBuffer` oder `pchBuffer` ist NULL.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosting](index.md)
