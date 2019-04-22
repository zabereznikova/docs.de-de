---
title: ICorPublishEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eac0b9fe252e476f8ff781f2181a203886d3beb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160133"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum-Schnittstelle
Dient als abstrakte Basisschnittstelle für die Enumeratoren, die die Veröffentlichung von Informationen zu Prozessen und Anwendungsdomänen verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Erstellt eine Kopie dieses `ICorPublishEnum` Objekt.|  
|[GetCount-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Ruft die Anzahl der Elemente in der Enumeration.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Verschiebt den Cursor auf den Anfang der Enumeration.|  
|[Skip-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Verschiebt den Cursor vorwärts in der Enumeration, um die angegebene Anzahl von Elementen.|  
  
## <a name="remarks"></a>Hinweise  
 Leiten Sie die folgenden Enumeratoren von `ICorPublishEnum`:  
  
-   [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CorpubPublish-Co-Klasse](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
