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
ms.openlocfilehash: f881440b2e93745723bd090cfbab0286dcd0a4e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937878"
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore-Schnittstelle
Stellt Methoden bereit, die einem Host das Laden von Assemblys und Modulen unabhängig von der Common Language Runtime (CLR) ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ProvideAssembly-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Ruft einen Verweis auf eine Assembly ab, auf die von der [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die von einem [IHostAssemblyManager:: getnonhoststoreassemblys](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)zurückgegeben wurde, nicht verwiesen wird.|  
|[ProvideModule-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Löst ein Modul in einer Assembly oder einer verknüpften (nicht eingebetteten) Ressourcen Datei auf.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostAssemblyStore`ermöglicht einem Host das effiziente Laden von Assemblys basierend auf der Assemblyidentität. Der Host lädt Assemblys `IStream` , indem er Instanzen zurückgibt, die direkt auf die Bytes zeigen.  
  
 Die CLR bestimmt, ob ein Host durch `IHostAssemblyStore` aufrufen `IHostAssemblyManager::GetNonHostAssemblyStores` von bei der Initialisierung implementiert wurde. Dadurch kann der Host z. b. die Bindung an Benutzerassemblys steuern, sich jedoch auf die Laufzeit zum Binden an .NET Framework Assemblys verlassen.  
  
> [!NOTE]
> Beim Bereitstellen einer Implementierung `IHostAssemblyStore`von gibt der Host seine Absicht an, alle Assemblys aufzulösen, auf die `ICLRAssemblyReferenceList` nicht von `IHostAssemblyManager::GetNonHostStoreAssemblies`der zurückgegebenen verwiesen wird.  
  
> [!NOTE]
> Der .NET Framework Version 2,0 bietet dem Host keine Möglichkeit, das systemeigene Image einer Assembly zu laden, wie vom systemeigenen [Image Generator (Ngen. exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) bereitgestellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
