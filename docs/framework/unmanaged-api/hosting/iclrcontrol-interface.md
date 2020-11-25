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
ms.openlocfilehash: acf449014f5bf5683d5488f8ed2ead963676fe6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728328"
---
# <a name="iclrcontrol-interface"></a>ICLRControl-Schnittstelle

Stellt Methoden bereit, mit denen ein Host Verweise auf die Common Language Runtime (CLR) erhalten und Aspekte von diesen konfigurieren kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetCLRManager-Methode](iclrcontrol-getclrmanager-method.md)|Ruft einen Schnittstellen Zeiger auf eine Instanz eines beliebigen Manager Typs ab, der vom Host zum Konfigurieren der CLR verwendet werden kann.|  
|[SetAppDomainManagerType-Methode](iclrcontrol-setappdomainmanagertype-method.md)|Legt einen von abgeleiteten Typ <xref:System.AppDomainManager> als Typ für Anwendungs Domänen-Manager fest.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager-Schnittstelle](iclrdebugmanager-interface.md)
- [ICLRGCManager-Schnittstelle](iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager-Schnittstelle](iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager-Schnittstelle](iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager-Schnittstelle](iclroneventmanager-interface.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
