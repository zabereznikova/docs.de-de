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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8c8d17723481fc5b41fe5f3006fe8db2c53d1ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438479"
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
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
