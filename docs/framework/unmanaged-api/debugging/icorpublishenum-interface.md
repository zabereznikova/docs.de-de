---
title: ICorPublishEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum
helpviewer_keywords: ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7034945824e439b42134f8ea3c13bfaf73dbb649
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum-Schnittstelle
Dient als abstrakte Basisschnittstelle für die Enumeratoren, die die Veröffentlichung von Informationen über Prozesse und Anwendungsdomänen verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Erstellt eine Kopie dieser `ICorPublishEnum` Objekt.|  
|[GetCount-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Ruft die Anzahl der Elemente in der Enumeration.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Verschiebt den Cursor auf den Anfang der Enumeration.|  
|[Skip-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Enumeratoren leiten sich von `ICorPublishEnum`:  
  
-   [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CorpubPublish-Co-Klasse](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
