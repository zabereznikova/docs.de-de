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
ms.openlocfilehash: a5abb601fe795a0c615403eec69f68ad9f66f00f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681170"
---
# <a name="iclrdomainmanager-interface"></a>ICLRDomainManager-Schnittstelle

Ermöglicht es dem Host, den Anwendungs Domänen-Manager anzugeben, der verwendet wird, um die Standard Anwendungsdomäne zu initialisieren und Initialisierungs Eigenschaften anzugeben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetAppDomainManagerType-Methode](iclrdomainmanager-setappdomainmanagertype-method.md)|Gibt den von der-Klasse abgeleiteten Typ <xref:System.AppDomainManager?displayProperty=nameWithType> des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.|  
|[SetPropertiesForDefaultAppDomain-Methode](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Legt Eigenschaften fest, die verwendet werden, um die Standard Anwendungsdomäne zu initialisieren.|  
  
## <a name="remarks"></a>Hinweise  

 Um eine Instanz dieser Schnittstelle abzurufen, wenden Sie die [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode mit dem Manager-Typ IID an `IID_ICLRDomainManager` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
