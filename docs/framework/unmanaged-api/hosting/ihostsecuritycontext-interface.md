---
title: IHostSecurityContext-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: 993d16818b25dfefe1f53c7afd06bc9857d9eb24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121520"
---
# <a name="ihostsecuritycontext-interface"></a>IHostSecurityContext-Schnittstelle
Ermöglicht dem Common Language Runtime (CLR), Sicherheitskontext Informationen beizubehalten, die vom Host implementiert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Capture-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Ruft einen Klon der `IHostSecurityContext` Instanz ab, die von einem [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)-Befehl zurückgegeben wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den CLR-als auch durch den Benutzercode steuern. Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden. `IHostSecurityContext` kapselt diese Sicherheitskontext Informationen, die für die Laufzeit nicht transparent sind. Die Common Language Runtime erfasst diese Informationen mithilfe `Capture`und verschiebt Sie über die Verteilung des workerelements des Thread Pools, die Finalizer-Ausführung sowie Module-und Klassenkonstruktoren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRHostProtectionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
