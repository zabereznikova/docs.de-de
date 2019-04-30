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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61fce3e06b5245872f7061716e8d995dd5f5043c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984645"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification-Methode
Bietet eine Rückruffunktion, die garantiert aufgerufen werden, wenn eine Version der common Language Runtime (CLR) zum ersten Mal geladen, aber noch nicht gestartet. Diese Methode ersetzt die [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCallbackFunction`  
 [in] Die Rückruffunktion, die aufgerufen wird, wenn eine neue Laufzeit geladen wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pCallbackFunction` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Der Rückruf funktioniert wie folgt:  
  
- Der Rückruf erfolgt nur, wenn eine Laufzeit zum ersten Mal geladen wird.  
  
- Der Rückruf ist nicht für wiedereintrittsfähige lädt der gleichen Laufzeit aufgerufen.  
  
- Für nicht wieder eintretender Laufzeit geladen wird werden Aufrufe an die Rückruffunktion serialisiert.  
  
 Die Callback-Funktion hat den folgenden Prototyp:  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 Die Rückruf-Funktionsprototypen lauten wie folgt aus:  
  
- `pfnCallbackThreadSet`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- `pfnCallbackThreadUnset`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Wenn der Host beabsichtigt zu laden oder dazu führen, dass eine andere Runtime auf eine Weise wiedereintrittsfähige geladen werden die `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` Parameter bereitgestellte Funktion in der Rückruffunktion auf folgende Weise verwendet werden muss:  
  
- `pfnCallbackThreadSet` muss durch den Thread aufgerufen werden, die Laden der Laufzeit führen kann, bevor, eine solche Last versucht wird.  
  
- `pfnCallbackThreadUnset` muss aufgerufen werden, wenn der Thread nicht mehr Laden der Laufzeit bewirkt (und vor der Rückgabe aus dem ersten Rückruf).  
  
- `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` sind beide nicht wiedereintrittsfähig.  
  
> [!NOTE]
>  Hosten von Anwendungen müssen nicht aufrufen, `pfnCallbackThreadSet` und `pfnCallbackThreadUnset` außerhalb des Bereichs der `pCallbackFunction` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
