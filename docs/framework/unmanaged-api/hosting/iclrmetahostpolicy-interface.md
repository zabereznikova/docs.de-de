---
title: ICLRMetaHostPolicy-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93507ac72b79210dc3a267fea39a6a7b2874916a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188565"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy-Schnittstelle
Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode, die einen Zeiger auf eine common Language Runtime (CLR)-Schnittstelle basierend auf einer Richtlinienkriterien zurückgibt, verwalteten Assembly, Version und Konfiguration.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|Bietet eine bevorzugte CLR-Schnittstelle auf der Grundlage einer Richtlinienkriterien, einer verwalteten Assembly, Version und Konfiguration.|  
  
## <a name="remarks"></a>Hinweise  
 Sie erhalten einen Verweis auf diese Schnittstelle durch Aufrufen der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) -Funktion wie im folgenden Code gezeigt:  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  Diese Schnittstelle nicht lädt oder aktiviert die CLR, sondern einfach gibt die bevorzugte CLR-Version anhand der verfügbaren Versionen, die installiert oder geladen werden.  
  
 Die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Richtlinien hosting-API konsolidiert werden, sodass Hosts mit bestimmten Anforderungen an die grundlegenden Funktionen verwenden können, ohne dass unbeabsichtigte Folge haben. Viele der Exporte "Mscoree.dll" werden z. B. auf eine bestimmte CLR binden, obwohl es sich bei eine Methode nicht logisch erforderlich ist. Die [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) Enumeration bietet Bindungsrichtlinien für die, die für die Mehrzahl der Hosts gelten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
