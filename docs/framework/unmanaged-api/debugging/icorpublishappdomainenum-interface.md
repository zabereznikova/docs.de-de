---
title: ICorPublishAppDomainEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 5b5a901bef779948467cfcc3d71a1fcd057c1aeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693709"
---
# <a name="icorpublishappdomainenum-interface"></a>ICorPublishAppDomainEnum-Schnittstelle

Eine Unterklasse der [ICorPublishEnum](icorpublishenum-interface.md) -Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von [ICorPublishAppDomain](icorpublishappdomain-interface.md) -Objekten bereitstellt, die derzeit in einem Prozess vorhanden sind.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Next-Methode](icorpublishappdomainenum-next-method.md)|Ruft die angegebene Anzahl von- `ICorPublishAppDomain` Instanzen ab der aktuellen Position aus der Auflistung ab.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `ICorPublishAppDomainEnum` Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
