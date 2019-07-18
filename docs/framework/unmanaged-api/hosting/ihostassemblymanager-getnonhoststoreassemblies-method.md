---
title: IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3680721c70ab69776c973913d929f7bdd9db3909
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779445"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
Ruft einen Schnittstellenzeiger auf ein [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , das die Liste der Assemblys, die der Host erwartet, die common Language Runtime (CLR) beim Laden dass darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppReferenceList`  
 [out] Ein Zeiger auf die Adresse einer `ICLRAssemblyReferenceList` , enthält eine Liste der Verweise auf Assemblys, die der Host erwartet, dass die CLR geladen.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die Liste der Verweise für die angeforderte erstellen `ICLRAssemblyReferenceList`.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR löst Verweise, die mithilfe der folgenden Richtlinien:  
  
- Zuerst herangezogen, die Liste von Assemblyverweisen, die vom `GetNonHostStoreAssemblies`.  
  
- Wenn die Assembly in der Liste angezeigt wird, wird die CLR, die normalerweise gebunden.  
  
- Wenn die Assembly nicht in der Liste angezeigt, und der Host eine Implementierung von stellt [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), die CLR ruft [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) auf den Host ermöglichen die die Assembly zum Binden an.  
  
- Andernfalls kann die CLR auf die Assembly zu binden.  
  
 Wenn der Host setzt `ppReferenceList` Aufrufe im globalen Assemblycache, null, durchsucht die CLR zuerst `ProvideAssembly`, und von Tests, klicken Sie dann die Anwendungsbasis, um einen Assemblyverweis aufzulösen.  
  
> [!NOTE]
>  Bei der Initialisierung, die CLR ruft `GetNonHostStoreAssemblies` nur einmal. Die Methode wird nicht erneut aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
