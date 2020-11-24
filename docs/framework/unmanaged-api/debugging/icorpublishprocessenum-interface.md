---
title: ICorPublishProcessEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: ebf484524b32d8e917d88c21425fab314dfc41be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692617"
---
# <a name="icorpublishprocessenum-interface"></a>ICorPublishProcessEnum-Schnittstelle

Eine Unterklasse der [ICorPublishEnum](icorpublishenum-interface.md) -Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von [ICorPublishProcess](icorpublishprocess-interface.md) -Objekten bereitstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Next-Methode](icorpublishprocessenum-next-method.md)|Ruft die angegebene Anzahl von- `ICorPublishProcess` Instanzen ab der aktuellen Position aus der Auflistung ab.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `ICorPublishProcessEnum` Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](icorpublishenum-interface.md).  
  
 Eine `ICorPublishProcessEnum` Instanz wird von der [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) -Methode erstellt. Der Durchlauf der Auflistung von `ICorPublishProcess` Objekten basiert auf den Filterkriterien, die zum Zeitpunkt der `ICorPublishProcessEnum` Erstellung der Instanz angegeben wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
