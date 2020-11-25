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
ms.openlocfilehash: 515b73b019c683bd3e5aa3b895ee5623e75e4ad0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707606"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy-Schnittstelle

Stellt die [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode bereit, die einen Zeiger auf eine Common Language Runtime (CLR)-Schnittstelle basierend auf einem Richtlinien Kriterium, einer verwalteten Assembly, einer Version und einer Konfigurationsdatei zurückgibt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetRequestedRuntime-Methode](iclrmetahostpolicy-getrequestedruntime-method.md)|Bietet eine bevorzugte CLR-Schnittstelle, die auf Richtlinien Kriterien, verwalteten Assemblys, Versionen und Konfigurationsdateien basiert.|  
  
## <a name="remarks"></a>Hinweise  

 Sie können einen Verweis auf diese Schnittstelle abrufen, indem Sie die [CLRCreateInstance](clrcreateinstance-function.md) -Funktion aufrufen, wie im folgenden Code gezeigt:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> Diese Schnittstelle lädt oder aktiviert die CLR nicht, sondern gibt einfach die bevorzugte CLR-Version basierend auf den verfügbaren installierten oder geladenen Versionen zurück.  
  
 Die .NET Framework 4-Hosting-API konsolidiert Richtlinien, sodass Hosts mit speziellen Anforderungen grundlegende Funktionen verwenden können, ohne dass dabei unbeabsichtigte Strafen anfallen. Beispielsweise werden viele der MSCorEE.dll Exporte an eine bestimmte CLR gebunden, obwohl eine Methode dies möglicherweise nicht logisch erfordert. Die [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) -Enumeration stellt Bindungs Richtlinien bereit, die für die Mehrzahl der Hosts üblich sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
