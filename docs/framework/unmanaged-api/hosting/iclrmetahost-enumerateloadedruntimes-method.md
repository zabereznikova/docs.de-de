---
title: ICLRMetaHost::EnumerateLoadedRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: f89307ad7ed41f872ad66a99be03663ac1f30f13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140972"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a>ICLRMetaHost::EnumerateLoadedRuntimes-Methode
Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede Version der Common Language Runtime (CLR) enthält, die in einem bestimmten Prozess geladen wird. Diese Methode ersetzt die [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) -Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hndProcess`  
 in Das Handle des Prozesses, der auf geladene Runtimes überprüft werden soll.  
  
 `ppEnumerator`  
 vorgenommen Eine <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Enumeration von [iclrruntimeingefo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstellen, die den einzelnen CLR entsprechen, die vom Prozess geladen werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`ppEnumerator` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode listet alle geladenen Runtimes auf, auch wenn Sie mit veralteten Funktionen wie [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)geladen wurden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
