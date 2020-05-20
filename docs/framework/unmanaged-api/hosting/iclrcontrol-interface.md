---
title: ICLRControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615836"
---
# <a name="iclrcontrol-interface"></a>ICLRControl-Schnittstelle
Stellt Methoden bereit, mit denen ein Host Verweise auf die Common Language Runtime (CLR) erhalten und Aspekte von diesen konfigurieren kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetCLRManager-Methode](iclrcontrol-getclrmanager-method.md)|Ruft einen Schnittstellen Zeiger auf eine Instanz eines beliebigen Manager Typs ab, der vom Host zum Konfigurieren der CLR verwendet werden kann.|  
|[SetAppDomainManagerType-Methode](iclrcontrol-setappdomainmanagertype-method.md)|Legt einen von abgeleiteten Typ <xref:System.AppDomainManager> als Typ für Anwendungs Domänen-Manager fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager-Schnittstelle](iclrdebugmanager-interface.md)
- [ICLRGCManager-Schnittstelle](iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager-Schnittstelle](iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager-Schnittstelle](iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager-Schnittstelle](iclroneventmanager-interface.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
