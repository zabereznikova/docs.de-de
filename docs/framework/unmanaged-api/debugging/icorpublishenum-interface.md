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
ms.openlocfilehash: f54bb99df60d7b3fb7bb98de75fbae210597e45c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790623"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum-Schnittstelle
Dient als abstrakte Basisschnittstelle für die Enumeratoren, die bei der Veröffentlichung von Informationen zu Prozessen und Anwendungs Domänen verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](icorpublishenum-clone-method.md)|Erstellt eine Kopie dieses `ICorPublishEnum` Objekts.|  
|[GetCount-Methode](icorpublishenum-getcount-method.md)|Ruft die Anzahl der Elemente in der-Enumeration ab.|  
|[Reset-Methode](icorpublishenum-reset-method.md)|Verschiebt den Cursor von an den Anfang der-Enumeration.|  
|[Skip-Methode](icorpublishenum-skip-method.md)|Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Enumeratoren werden von `ICorPublishEnum`abgeleitet:  
  
- [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
