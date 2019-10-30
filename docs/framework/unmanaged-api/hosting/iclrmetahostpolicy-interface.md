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
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140860"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy-Schnittstelle
Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode bereit, die einen Zeiger auf eine Common Language Runtime (CLR)-Schnittstelle basierend auf einem Richtlinien Kriterium, einer verwalteten Assembly, einer Version und einer Konfigurationsdatei zurückgibt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|Bietet eine bevorzugte CLR-Schnittstelle, die auf Richtlinien Kriterien, verwalteten Assemblys, Versionen und Konfigurationsdateien basiert.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können einen Verweis auf diese Schnittstelle abrufen, indem Sie die [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) -Funktion aufrufen, wie im folgenden Code gezeigt:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> Diese Schnittstelle lädt oder aktiviert die CLR nicht, sondern gibt einfach die bevorzugte CLR-Version basierend auf den verfügbaren installierten oder geladenen Versionen zurück.  
  
 Die .NET Framework 4-Hosting-API konsolidiert Richtlinien, sodass Hosts mit speziellen Anforderungen grundlegende Funktionen verwenden können, ohne dass dabei unbeabsichtigte Strafen anfallen. Beispielsweise werden viele der Mscoree. dll-Exporte an eine bestimmte CLR gebunden, obwohl eine Methode dies möglicherweise nicht logisch erfordert. Die [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) -Enumeration stellt Bindungs Richtlinien bereit, die für die Mehrzahl der Hosts gemeinsam sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
