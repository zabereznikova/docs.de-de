---
title: CorpubPublish-Co-Klasse
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: e33029e8244fdfa180a79aa4a5b05b07f594d928
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860909"
---
# <a name="corpubpublish-coclass"></a>CorpubPublish-Co-Klasse
Stellt Schnittstellen für die Veröffentlichung von Informationen über Anwendungsdomänen und Prozesse bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Schnittstelle|BESCHREIBUNG|  
|---------------|-----------------|  
|[ICorPublish-Schnittstelle](icorpublish-interface.md)|Stellt Methoden zum Veröffentlichen von Informationen zu Prozessen und Anwendungs Domänen in diesen Prozessen bereit.|  
|[ICorPublishAppDomain-Schnittstelle](icorpublishappdomain-interface.md)|Stellt eine Anwendungsdomäne in einem Prozess dar und stellt Informationen zu einer Anwendungsdomäne bereit.|  
|[ICorPublishAppDomainEnum-Schnittstelle](icorpublishappdomainenum-interface.md)|Stellt Methoden bereit, die eine Auflistung von Anwendungs Domänen durchlaufen, die derzeit in einem Prozess vorhanden sind.|  
|[ICorPublishProcess-Schnittstelle](icorpublishprocess-interface.md)|Stellt einen Prozess dar, der auf einem Computer ausgeführt wird.|  
|[ICorPublishProcessEnum-Schnittstelle](icorpublishprocessenum-interface.md)|Stellt Methoden bereit, die eine Auflistung von Prozessen durchlaufen, die auf einem Computer ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein typisches Veröffentlichungs Szenario umfasst einen Entwickler, der verwalteten Code Debuggen möchte, der auf einem Computer innerhalb einer Anwendungsdomäne ausgeführt wird. In der Hostingumgebung wird möglicherweise mehr als eine Anwendungsdomäne innerhalb eines Prozesses ausgeführt. Der Entwickler möchte eine grafische Benutzeroberfläche oder andere Mittel verwenden, um alle Prozesse aufzulisten, die auf dem Computer ausgeführt werden, und einen bestimmten Prozess auszuwählen. Die Auflistung sollte alle Anwendungs Domänen innerhalb von Prozessen enthalten, die verwalteten Code ausführen. Der Entwickler kann dann die jeweilige Anwendungsdomäne identifizieren und dieser Domäne einen Debugger anfügen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Debuggen](index.md)
