---
title: ICLRRuntimeInfo::IsLoaded-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136364"
---
# <a name="iclrruntimeinfoisloaded-method"></a>ICLRRuntimeInfo::IsLoaded-Methode
Gibt an, ob die der [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zugeordnete Common Language Runtime (CLR) in einen Prozess geladen wird. Eine Laufzeit kann geladen werden, ohne dass Sie auch gestartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a>Parameter  
 `hndProcess`  
 in Ein Handle für den Prozess.  
  
 `pbLoaded`  
 [out] `true`, wenn die CLR in den Prozess geladen wird. Andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pbLoaded` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist abwärts kompatibel mit den folgenden Funktionen und Schnittstellen:  
  
- [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -Schnittstelle (in der .NET Framework, Version 1-Hosting-API).  
  
- [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) -Schnittstelle (in der .NET Framework 2,0-Hosting-API).  
  
- Veraltete `CorBindTo*` Funktionen (siehe [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in der .NET Framework 2,0-Hosting-API).  
  
 Ein Host kann eine der veralteten `CorBindTo*` Funktionen aufrufen, z. b. die [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) -Funktion, um eine bestimmte Version der CLR zu instanziieren. Der Host kann dann die [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) -Methode aufzurufen und die gleiche Versionsnummer angeben, um eine [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zu erhalten.  
  
 Wenn der Host dann die `IsLoaded`-Methode für die zurückgegebene [iclrruntimeingefo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle aufruft, gibt `pbLoaded` `true`zurück. Andernfalls wird `false`zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
