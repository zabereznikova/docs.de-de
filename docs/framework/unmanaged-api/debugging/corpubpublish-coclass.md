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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9941a9be7d9f68255636b405db29a623be8d37e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corpubpublish-coclass"></a>CorpubPublish-Co-Klasse
Stellt Schnittstellen für die Veröffentlichung von Informationen über Anwendungsdomänen und Prozesse bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|[ICorPublish-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Stellt Methoden für die Veröffentlichung von Informationen über Prozesse und die Anwendungsdomänen in diesen Prozessen bereit.|  
|[ICorPublishAppDomain-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Stellt dar, und enthält Informationen zu einer Anwendungsdomäne in einem Prozess.|  
|[ICorPublishAppDomainEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Enthält Methoden, die eine Auflistung von Anwendungsdomänen durchlaufen, die derzeit innerhalb eines Prozesses vorhanden sind.|  
|[ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Entspricht einem Prozess, der auf einem Computer ausgeführt wird.|  
|[ICorPublishProcessEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Enthält Methoden, die eine Auflistung von Prozessen durchlaufen, die auf einem Computer ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein typisches Szenario für die publishing umfasst einen Entwickler möchte, Debuggen Sie verwalteten Code, der auf einem Computer in einer Anwendungsdomäne ausgeführt wird. Die hostumgebung möglicherweise mehr als eine Anwendungsdomäne innerhalb eines Prozesses ausgeführt. Der Entwickler möchte eine grafische Benutzeroberfläche oder andere Weise verwenden, um alle Prozesse aufzulisten, die auf dem Computer ausgeführt werden, und wählen Sie einen bestimmten Prozess. Die Auflistung sollte alle Anwendungsdomänen innerhalb von Prozessen enthalten, die verwalteten Code ausgeführt werden. Klicken Sie dann kann den bestimmten Anwendungsdomäne zu identifizieren und Anfügen eines Debuggers an, dass diese Domäne.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
