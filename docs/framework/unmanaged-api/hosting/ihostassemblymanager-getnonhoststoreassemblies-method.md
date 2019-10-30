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
ms.openlocfilehash: eb715e1a4f9a210a1440874a9a8cea2d85345d33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124578"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host erwartet, dass die Common Language Runtime (CLR) geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppReferenceList`  
 vorgenommen Ein Zeiger auf die Adresse einer `ICLRAssemblyReferenceList`, die eine Liste der Verweise auf Assemblys enthält, die der Host erwartet, dass die CLR geladen wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die Liste der Verweise für die angeforderte `ICLRAssemblyReferenceList`zu erstellen.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR löst Verweise mithilfe der folgenden Richtlinien auf:  
  
- Zuerst wird die Liste der von `GetNonHostStoreAssemblies`zurückgegebenen Assemblyverweise konsultiert.  
  
- Wenn die Assembly in der Liste angezeigt wird, bindet die CLR Sie normal an Sie.  
  
- Wenn die Assembly nicht in der Liste angezeigt wird und der Host eine Implementierung von [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)bereitgestellt hat, ruft die CLR [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) auf, damit der Host die Assembly bereitstellen kann, an die die Bindung erfolgen soll.  
  
- Andernfalls kann die CLR nicht an die Assembly gebunden werden.  
  
 Wenn der Host `ppReferenceList` auf NULL festlegt, testet die CLR zuerst den globalen Assemblycache, ruft `ProvideAssembly`auf und testet dann die Anwendungs Basis, um einen Assemblyverweis aufzulösen.  
  
> [!NOTE]
> Bei der Initialisierung Ruft die CLR `GetNonHostStoreAssemblies` nur einmal auf. Die Methode wird nicht erneut aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
