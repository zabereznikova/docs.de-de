---
title: ICLRMetaHostPolicy-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy
helpviewer_keywords: ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b8cbe1d397e1214cfa4d3f4cbc3d6cdf2d3ccd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy-Schnittstelle
Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode, die einen Zeiger auf eine common Language Runtime (CLR)-Schnittstelle basierend auf einer Richtlinie Kriterien zurückgibt, verwaltete Assembly, die Version und die Konfigurationsdatei.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|Bietet eine bevorzugte CLR-Schnittstelle auf der Grundlage einer Richtlinie Kriterien sowie eine verwaltete Assembly, die Version und die Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Sie erhalten einen Verweis auf diese Schnittstelle durch Aufrufen der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) -Funktion wie im folgenden Code gezeigt:  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  Diese Schnittstelle nicht lädt oder aktiviert die CLR, sondern einfach gibt die bevorzugte CLR-Version anhand der verfügbaren Versionen, die installiert oder geladen werden.  
  
 Die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Richtlinien hosting-API konsolidiert werden, sodass die Hosts mit spezifischen Anforderungen Grundfunktionen verwenden können, ohne dass das unbeabsichtigte Strafen anfallen. Beispielsweise werden viele der Exporte "Mscoree.dll" zu einer bestimmten CLR binden, obwohl eine Methode nicht logisch erfordert möglicherweise. Die [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) Enumeration stellt Bindungsrichtlinien für die, die für die Mehrheit der Hosts gelten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-Hostingschnittstellen hinzugefügt in .NET Framework 4 und 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
