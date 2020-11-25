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
ms.openlocfilehash: 3ff4efe8b3e2932da7f65246bf4ad614a4dd86cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694411"
---
# <a name="icorpublish-interface"></a>ICorPublish-Schnittstelle

Dient als allgemeine Schnittstelle zum Veröffentlichen von Informationen zu Prozessen und Informationen zu den Anwendungs Domänen in diesen Prozessen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumProcesses-Methode](icorpublish-enumprocesses-method.md)|Ruft eine [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) -Instanz ab, die die verwalteten Prozesse enthält, die auf diesem Computer ausgeführt werden.|  
|[GetProcess-Methode](icorpublish-getprocess-method.md)|Ruft eine [ICorPublishProcess](icorpublishprocess-interface.md) -Instanz ab, die den Prozess mit dem angegebenen Bezeichner darstellt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
