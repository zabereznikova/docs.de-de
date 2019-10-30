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
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124510"
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager-Schnittstelle
Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die vom Common Language Runtime (CLR) oder vom Host geladen werden sollen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAssemblyStore-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|Ruft einen Schnittstellen Zeiger auf einen [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) ab, der die Liste der vom Host geladenen Assemblys darstellt.|  
|[GetNonHostStoreAssemblies-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host zum Laden der CLR erwartet.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host muss `IHostAssemblyManager` oder `IHostAssemblyStore`nicht implementieren. Wenn der Host `IHostAssemblyManager`implementiert, muss auch `IHostAssemblyStore`implementiert werden.  
  
 Die Laufzeit fragt eine `IHostAssemblyManager` ab, indem Sie [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einer `IID` von IID_IHostAssemblyManager aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
