---
title: ICorPublishProcess-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8ee59e9d416d1c53312e4fccb6953f20b03b29b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693085"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess-Schnittstelle

Stellt Methoden bereit, die auf Informationen zugreifen, die zu einem Prozess angezeigt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumAppDomains-Methode](icorpublishprocess-enumappdomains-method.md)|Ruft eine [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) -Instanz ab, die die Anwendungs Domänen in dem Prozess enthält, auf den von verwiesen wird `ICorPublishProcess` .|  
|[GetDisplayName-Methode](icorpublishprocess-getdisplayname-method.md)|Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess ab, auf den von verwiesen wird `ICorPublishProcess` .|  
|[GetProcessID-Methode](icorpublishprocess-getprocessid-method.md)|Ruft den Betriebssystem Bezeichner für den Prozess ab, auf den von verwiesen wird `ICorPublishProcess` .|  
|[IsManaged-Methode](icorpublishprocess-ismanaged-method.md)|Ruft einen Wert ab, der angibt, ob der Prozess, auf den von verwiesen wird `ICorPublishProcess` , bekanntermaßen verwalteten Code ausgeführt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
