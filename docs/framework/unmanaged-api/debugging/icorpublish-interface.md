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
ms.openlocfilehash: 70cf2d76c7c5d1c3431506685f8506e44ab9ec4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121769"
---
# <a name="icorpublish-interface"></a>ICorPublish-Schnittstelle
Dient als allgemeine Schnittstelle zum Veröffentlichen von Informationen zu Prozessen und Informationen zu den Anwendungs Domänen in diesen Prozessen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumProcesses-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|Ruft eine [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) -Instanz ab, die die verwalteten Prozesse enthält, die auf diesem Computer ausgeführt werden.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz ab, die den Prozess mit dem angegebenen Bezeichner darstellt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
