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
ms.openlocfilehash: 9a1440be7011130b16d7112ae15026eb74856190
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501591"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host erwartet, dass die Common Language Runtime (CLR) geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppReferenceList`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICLRAssemblyReferenceList` , der eine Liste der Verweise auf Assemblys enthält, die der Host erwartet, dass die CLR geladen wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die Liste der Verweise für den angeforderten zu erstellen `ICLRAssemblyReferenceList` .|  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR löst Verweise mithilfe der folgenden Richtlinien auf:  
  
- Zuerst wird die Liste der von zurückgegebenen Assemblyverweise konsultiert `GetNonHostStoreAssemblies` .  
  
- Wenn die Assembly in der Liste angezeigt wird, bindet die CLR Sie normal an Sie.  
  
- Wenn die Assembly nicht in der Liste angezeigt wird und der Host eine Implementierung von [IHostAssemblyStore](ihostassemblystore-interface.md)bereitgestellt hat, ruft die CLR [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) auf, damit der Host die Assembly bereitstellen kann, an die die Bindung erfolgen soll.  
  
- Andernfalls kann die CLR nicht an die Assembly gebunden werden.  
  
 Wenn der Host `ppReferenceList` auf NULL festlegt, testet die CLR zuerst den globalen Assemblycache, ruft auf `ProvideAssembly` und testet dann die Anwendungs Basis, um einen Assemblyverweis aufzulösen.  
  
> [!NOTE]
> Bei der Initialisierung Ruft die CLR `GetNonHostStoreAssemblies` nur einmal auf. Die Methode wird nicht erneut aufgerufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](ihostassemblystore-interface.md)
