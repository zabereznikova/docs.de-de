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
ms.openlocfilehash: 4e32a36a4cf751bf7c5a2c918fde0122f21b7878
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501590"
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager-Schnittstelle
Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die vom Common Language Runtime (CLR) oder vom Host geladen werden sollen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetAssemblyStore-Methode](ihostassemblymanager-getassemblystore-method.md)|Ruft einen Schnittstellen Zeiger auf einen [IHostAssemblyStore](ihostassemblystore-interface.md) ab, der die Liste der vom Host geladenen Assemblys darstellt.|  
|[GetNonHostStoreAssemblies-Methode](ihostassemblymanager-getnonhoststoreassemblies-method.md)|Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host zum Laden der CLR erwartet.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Host muss oder nicht implementieren `IHostAssemblyManager` `IHostAssemblyStore` . Wenn der Host implementiert `IHostAssemblyManager` , muss auch implementiert werden `IHostAssemblyStore` .  
  
 Die Lauf Zeit Abfrage für einen `IHostAssemblyManager` durch Aufrufen von [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einem `IID` IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyStore-Schnittstelle](ihostassemblystore-interface.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
