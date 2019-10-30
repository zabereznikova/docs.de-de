---
title: ICLRDomainManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129339"
---
# <a name="iclrdomainmanager-interface"></a>ICLRDomainManager-Schnittstelle
Ermöglicht es dem Host, den Anwendungs Domänen-Manager anzugeben, der verwendet wird, um die Standard Anwendungsdomäne zu initialisieren und Initialisierungs Eigenschaften anzugeben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetAppDomainManagerType-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|Gibt den von der <xref:System.AppDomainManager?displayProperty=nameWithType>-Klasse abgeleiteten Typ des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.|  
|[SetPropertiesForDefaultAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Legt Eigenschaften fest, die verwendet werden, um die Standard Anwendungsdomäne zu initialisieren.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Instanz dieser Schnittstelle abzurufen, müssen Sie die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode mit dem Manager-Typ IID `IID_ICLRDomainManager`aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
