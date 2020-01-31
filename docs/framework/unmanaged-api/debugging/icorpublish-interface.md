---
title: ICorPublish-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790725"
---
# <a name="icorpublish-interface"></a>ICorPublish-Schnittstelle
Dient als allgemeine Schnittstelle zum Veröffentlichen von Informationen zu Prozessen und Informationen zu den Anwendungs Domänen in diesen Prozessen.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[EnumProcesses-Methode](icorpublish-enumprocesses-method.md)|Ruft eine [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) -Instanz ab, die die verwalteten Prozesse enthält, die auf diesem Computer ausgeführt werden.|  
|[GetProcess-Methode](icorpublish-getprocess-method.md)|Ruft eine [ICorPublishProcess](icorpublishprocess-interface.md) -Instanz ab, die den Prozess mit dem angegebenen Bezeichner darstellt.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
