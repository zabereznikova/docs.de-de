---
title: IHostAssemblyManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680986"
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager-Schnittstelle

Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die vom Common Language Runtime (CLR) oder vom Host geladen werden sollen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetAssemblyStore-Methode](ihostassemblymanager-getassemblystore-method.md)|Ruft einen Schnittstellen Zeiger auf einen [IHostAssemblyStore](ihostassemblystore-interface.md) ab, der die Liste der vom Host geladenen Assemblys darstellt.|  
|[GetNonHostStoreAssemblies-Methode](ihostassemblymanager-getnonhoststoreassemblies-method.md)|Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host zum Laden der CLR erwartet.|  
  
## <a name="remarks"></a>Hinweise  

 Der Host muss oder nicht implementieren `IHostAssemblyManager` `IHostAssemblyStore` . Wenn der Host implementiert `IHostAssemblyManager` , muss auch implementiert werden `IHostAssemblyStore` .  
  
 Die Lauf Zeit Abfrage für einen `IHostAssemblyManager` durch Aufrufen von [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einem `IID` IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyStore-Schnittstelle](ihostassemblystore-interface.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
