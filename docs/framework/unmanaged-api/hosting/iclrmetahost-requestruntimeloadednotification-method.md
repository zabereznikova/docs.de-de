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
ms.openlocfilehash: 6813f72f9d27aeff90f797a6ca9370b22e03e6f0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703706"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification-Methode
Stellt eine Rückruffunktion bereit, die garantiert aufgerufen wird, wenn eine Common Language Runtime (CLR)-Version zum ersten Mal geladen, aber noch nicht gestartet wurde. Diese Methode löst die [LockClrVersion](lockclrversion-function.md) -Funktion aus.  
  
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
  
|HRESULT|BESCHREIBUNG|  
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
  
 Wenn der Host geladen werden soll oder eine andere Laufzeit in eine Einstiegs Weise geladen werden soll, `pfnCallbackThreadSet` müssen die-und- `pfnCallbackThreadUnset` Parameter, die in der Rückruffunktion bereitgestellt werden, wie folgt verwendet werden:  
  
- `pfnCallbackThreadSet`muss vom Thread aufgerufen werden, der eine Lauf Zeit Auslastung verursachen kann, bevor ein solcher Ladevorgang versucht wird.  
  
- `pfnCallbackThreadUnset`muss aufgerufen werden, wenn der Thread eine solche Lauf Zeit Auslastung nicht mehr bewirkt (und bevor der anfängliche Rückruf zurückgegeben wird).  
  
- `pfnCallbackThreadSet`und `pfnCallbackThreadUnset` sind beide nicht Wiedereintritts fähig.  
  
> [!NOTE]
> Host Anwendungen dürfen nicht und außerhalb des Gültigkeits `pfnCallbackThreadSet` `pfnCallbackThreadUnset` Bereichs des- `pCallbackFunction` Parameters aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](iclrmetahost-interface.md)
- [Hosting](index.md)
