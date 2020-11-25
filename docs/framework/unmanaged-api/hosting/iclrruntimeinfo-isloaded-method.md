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
ms.openlocfilehash: 66ae74deba9ceab9d1ea6b2c0b96a87bf44f32ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714925"
---
# <a name="iclrruntimeinfoisloaded-method"></a>ICLRRuntimeInfo::IsLoaded-Methode

Gibt an, ob die der [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zugeordnete Common Language Runtime (CLR) in einen Prozess geladen wird. Eine Laufzeit kann geladen werden, ohne dass Sie auch gestartet wird.  
  
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
 [out] `true` , wenn die CLR in den Prozess geladen wird. andernfalls `false` .  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pbLoaded` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode ist abwärts kompatibel mit den folgenden Funktionen und Schnittstellen:  
  
- [ICorRuntimeHost](icorruntimehost-interface.md) -Schnittstelle (in der .NET Framework, Version 1-Hosting-API).  
  
- [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle (in der .NET Framework 2,0-Hosting-API).  
  
- Als veraltet markierte `CorBindTo*` Funktionen (siehe [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md) in der .NET Framework 2,0-Hosting-API).  
  
 Ein Host kann eine der veralteten `CorBindTo*` Funktionen aufrufen, z. b. die [CorBindToRuntime](corbindtoruntime-function.md) -Funktion, um eine bestimmte Version der CLR zu instanziieren. Der Host kann dann die [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) -Methode aufzurufen und die gleiche Versionsnummer angeben, um eine [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zu erhalten.  
  
 Wenn der Host die- `IsLoaded` Methode auf der zurückgegebenen [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle aufruft, `pbLoaded` gibt zurück, `true` andernfalls wird zurückgegeben `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
