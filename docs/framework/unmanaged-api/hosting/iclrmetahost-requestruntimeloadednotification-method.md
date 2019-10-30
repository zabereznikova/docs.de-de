---
title: ICLRMetaHost::RequestRuntimeLoadedNotification-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: 23f868bba2dc058d99f1c5c09e9b311b1ff3634a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140899"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification-Methode
Stellt eine Rückruffunktion bereit, die garantiert aufgerufen wird, wenn eine Common Language Runtime (CLR)-Version zum ersten Mal geladen, aber noch nicht gestartet wurde. Diese Methode löst die [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) -Funktion aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCallbackFunction`  
 in Die Rückruffunktion, die aufgerufen wird, wenn eine neue Laufzeit geladen wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pCallbackFunction` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Der Rückruf funktioniert wie folgt:  
  
- Der Rückruf wird nur aufgerufen, wenn eine Laufzeit zum ersten Mal geladen wird.  
  
- Der Rückruf wird nicht für Wiedereintritts fähige Ladevorgänge derselben Laufzeit aufgerufen.  
  
- Bei nicht wieder eintretende Lauf Zeit Ladevorgängen werden Aufrufe der Rückruffunktion serialisiert.  
  
 Die Rückruffunktion hat den folgenden Prototyp:  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 Die Rückruf Funktionsprototypen lauten wie folgt:  
  
- `pfnCallbackThreadSet`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- `pfnCallbackThreadUnset`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Wenn der Host geladen werden soll oder eine andere Laufzeit in eine Einstiegs Weise geladen werden soll, müssen die in der Rückruffunktion bereitgestellten `pfnCallbackThreadSet`-und `pfnCallbackThreadUnset` Parameter wie folgt verwendet werden:  
  
- `pfnCallbackThreadSet` müssen von dem Thread aufgerufen werden, der eine Lauf Zeit Auslastung verursachen kann, bevor ein solcher Ladevorgang versucht wird.  
  
- `pfnCallbackThreadUnset` müssen aufgerufen werden, wenn der Thread eine solche Lauf Zeit Auslastung nicht mehr bewirkt (und bevor der anfängliche Rückruf zurückgegeben wird).  
  
- `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` sind nicht Wiedereintritts fähig.  
  
> [!NOTE]
> Host Anwendungen dürfen `pfnCallbackThreadSet` nicht aufrufen und `pfnCallbackThreadUnset` außerhalb des Bereichs des `pCallbackFunction`-Parameters.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
