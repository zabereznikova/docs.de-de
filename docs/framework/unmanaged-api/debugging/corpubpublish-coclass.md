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
ms.openlocfilehash: 05d9eef36885aee05d88f7da994c8b168c3221b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130532"
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
|[ICorPublish-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Stellt Methoden für die Veröffentlichung von Informationen zu Prozessen und Anwendungsdomänen in diesen Prozessen bereit.|  
|[ICorPublishAppDomain-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Stellt dar, und enthält Informationen zu einer Anwendungsdomäne in einem Prozess.|  
|[ICorPublishAppDomainEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Bietet Methoden, die eine Auflistung von Anwendungsdomänen durchlaufen, die zurzeit innerhalb eines Prozesses vorhanden sind.|  
|[ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Stellt einen Prozess, der auf einem Computer ausgeführt wird.|  
|[ICorPublishProcessEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Bietet Methoden, die eine Auflistung der Prozesse durchlaufen, die auf einem Computer ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein typisches Szenario für die Veröffentlichung umfasst einen Entwickler möchte, verwalteten Code Debuggen, die auf einem Computer innerhalb einer Anwendungsdomäne ausgeführt wird. Die hostumgebung möglicherweise mehr als eine Anwendungsdomäne innerhalb eines Prozesses ausgeführt. Der Entwickler möchte eine grafische Benutzeroberfläche oder eine andere Möglichkeit zum Auflisten aller Prozesse, die auf dem Computer ausgeführt werden, und wählen Sie einen bestimmten Prozess. Die Liste sollte alle Anwendungsdomänen innerhalb von Prozessen enthalten, die verwalteten Code ausgeführt werden. Der Entwickler kann dann identifizieren die spezifischen Anwendungsdomäne und Anfügen eines Debuggers an der Domäne.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
