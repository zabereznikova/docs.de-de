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
ms.openlocfilehash: 492d4b727ce507340fec47d30a791aa49d0cecb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693345"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum-Schnittstelle

Dient als abstrakte Basisschnittstelle für die Enumeratoren, die bei der Veröffentlichung von Informationen zu Prozessen und Anwendungs Domänen verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Clone-Methode](icorpublishenum-clone-method.md)|Erstellt eine Kopie dieses `ICorPublishEnum`-Objekts.|  
|[GetCount-Methode](icorpublishenum-getcount-method.md)|Ruft die Anzahl der Elemente in der-Enumeration ab.|  
|[Reset-Methode](icorpublishenum-reset-method.md)|Verschiebt den Cursor von an den Anfang der-Enumeration.|  
|[Skip-Methode](icorpublishenum-skip-method.md)|Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.|  
  
## <a name="remarks"></a>Hinweise  

 Die folgenden Enumeratoren werden von abgeleitet `ICorPublishEnum` :  
  
- [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
- [Debugschnittstellen](debugging-interfaces.md)
