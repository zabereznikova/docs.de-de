---
title: ICLRRuntimeInfo::LoadErrorString-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762187"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a>ICLRRuntimeInfo::LoadErrorString-Methode
Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.  
  
 Diese Methode ersetzt die folgenden Funktionen:  
  
- [LoadStringRC](loadstringrc-function.md)  
  
- [LoadStringRCEx](loadstringrcex-function.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a>Parameter  
 `iResourceID`  
 in Das zu über setzende HRESULT.  
  
 `pwzBuffer`  
 vorgenommen Die dem angegebenen HRESULT zugeordnete Meldungs Zeichenfolge.  
  
 `pcchBuffer`  
 [in, out] Die Größe von `pwzbuffer` , um Pufferüberläufe zu vermeiden. Wenn `pwzbuffer` NULL ist, wird `pcchBuffer` die erwartete Größe von bereitgestellt `pwzbuffer` , um die vorab Zuordnung zuzulassen.  
  
 `iLocaleID`  
 in Der Kultur Bezeichner. Wenn Sie die Standard Kultur verwenden möchten, müssen Sie-1 angeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pcchBuffer` ist NULL.|  
|E_INVALIDARG|`pwzBuffer` ist NULL.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
