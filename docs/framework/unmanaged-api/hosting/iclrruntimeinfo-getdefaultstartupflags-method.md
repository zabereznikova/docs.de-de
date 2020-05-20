---
title: ICLRRuntimeInfo::GetDefaultStartupFlags-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 8513787f48ae89632816face386bbcda20555dac
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703884"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags-Methode
Ruft die startflags und die Host Konfigurationsdatei ab, die zum Starten der Laufzeit verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwStartupFlags`  
 vorgenommen Ein Zeiger auf die hoststartflags, die derzeit festgelegt sind.  
  
 `pwzHostConfigFile`  
 vorgenommen Ein Zeiger auf den Verzeichnispfad der aktuellen Host Konfigurationsdatei.  
  
 `pcchHostConfigFile`  
 [in, out] Bei Eingabe die Größe von `pwzHostConfigFile` , um Pufferüberläufe zu vermeiden. Wenn `pwzHostConfigFile` NULL ist, gibt die Methode die erforderliche Größe von `pwzHostConfigFile` für die vorab Zuordnung zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULT-und HRESULT-Fehler zurück, die auf Methoden Fehler hinweisen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt die standardflagwerte ( `STARTUP_CONCURRENT_GC` und `NULL` ) oder die Werte zurück, die durch einen vorherigen Aufrufen der [ICLRRuntimeInfo:: SetDefaultStartupFlags-Methode](iclrruntimeinfo-setdefaultstartupflags-method.md)bereitgestellt werden, oder die Werte, die von einer der-Methoden festgelegt werden, `CorBind*` Wenn Sie an diese Laufzeit gebunden sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
