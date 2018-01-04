---
title: IHostAssemblyManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager
helpviewer_keywords: IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 351824c1b915183a8e157f5bb2e01a414027a178
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager-Schnittstelle
Enthält Methoden, mit denen einen Host Sätze von Assemblys angeben, die von der common Language Runtime (CLR) oder vom Host geladen werden soll.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAssemblyStore-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|Ruft einen Schnittstellenzeiger auf eine [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , die die Liste der Assemblys, die vom Host geladen darstellt.|  
|[GetNonHostStoreAssemblies-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|Ruft einen Schnittstellenzeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die die Liste der Assemblys, die der Host die CLR geladen erwartet darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ist nicht erforderlich, um implementieren `IHostAssemblyManager` oder `IHostAssemblyStore`. Wenn der Host implementiert `IHostAssemblyManager`, müssen Sie auch implementieren `IHostAssemblyStore`.  
  
 Die Laufzeit fragt eine `IHostAssemblyManager` durch Aufrufen [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einer `IID` von IID_IHostAssemblyManager aufruft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
