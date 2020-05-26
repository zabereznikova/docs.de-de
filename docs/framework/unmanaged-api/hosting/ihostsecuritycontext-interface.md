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
ms.openlocfilehash: bf8e725908177d9a15407b096f68cbcb947c7a01
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804157"
---
# <a name="ihostsecuritycontext-interface"></a>IHostSecurityContext-Schnittstelle
Ermöglicht dem Common Language Runtime (CLR), Sicherheitskontext Informationen beizubehalten, die vom Host implementiert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Capture-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Ruft einen Klon der- `IHostSecurityContext` Instanz ab, die von einem [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)-Befehl zurückgegeben wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den CLR-als auch durch den Benutzercode steuern. Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden. `IHostSecurityContext`kapselt diese Sicherheitskontext Informationen, die für die Laufzeit nicht transparent sind. Die Laufzeit erfasst diese Informationen mithilfe von `Capture` und verschiebt Sie über die Verteilung des workerelements des Thread Pools, die Finalizer-Ausführung sowie Module-und Klassenkonstruktoren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRHostProtectionManager-Schnittstelle](iclrhostprotectionmanager-interface.md)
- [IHostSecurityManager-Schnittstelle](ihostsecuritymanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
