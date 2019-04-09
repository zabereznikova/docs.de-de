---
title: IHostAssemblyStore-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173419"
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore-Schnittstelle
Enthält Methoden, die einen Host zum Laden von Assemblys und Modulen unabhängig von der die common Language Runtime (CLR) zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ProvideAssembly-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Ruft einen Verweis auf eine Assembly, die nicht verwiesen wird die [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) zurückgegeben, die von einem Aufruf von [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[ProvideModule-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Löst ein Modul innerhalb einer Assembly oder eine verknüpfte (nicht eingebettete) Ressourcendatei an.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostAssemblyStore` bietet eine Möglichkeit für einen Host, Assemblys, die effizient basierend auf Assemblyidentität zu laden. Der Host lädt Assemblys durch Rückgabe `IStream` Instanzen, die direkt auf die Bytes zu verweisen.  
  
 Die CLR bestimmt, ob ein Host implementiert hat `IHostAssemblyStore` durch Aufrufen von `IHostAssemblyManager::GetNonHostAssemblyStores` bei der Initialisierung. Dies ermöglicht dem Host, z. B. zum Binden an die Benutzer-Assemblys zu steuern, aber von der Common Language Runtime zum Binden an .NET Framework-Assemblys abhängig zu sein.  
  
> [!NOTE]
>  Bereitstellen einer Implementierung von `IHostAssemblyStore`, gibt die Absicht, um alle Assemblys aufzulösen, die nicht verwiesen werden: der Host die `ICLRAssemblyReferenceList` Merry `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
>  .NET Framework, Version 2.0 bietet keine Möglichkeit für den Host, der das systemeigene Abbild von einer Assembly lädt, gemäß Bereitstellung durch die [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) Hilfsprogramm.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
