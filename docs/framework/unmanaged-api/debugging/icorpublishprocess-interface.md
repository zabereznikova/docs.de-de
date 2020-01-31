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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790541"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess-Schnittstelle
Stellt Methoden bereit, die auf Informationen zugreifen, die zu einem Prozess angezeigt werden.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[EnumAppDomains-Methode](icorpublishprocess-enumappdomains-method.md)|Ruft eine [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) -Instanz ab, die die Anwendungs Domänen in dem Prozess enthält, auf den von diesem `ICorPublishProcess`verwiesen wird.|  
|[GetDisplayName-Methode](icorpublishprocess-getdisplayname-method.md)|Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess ab, auf den von diesem `ICorPublishProcess`verwiesen wird.|  
|[GetProcessID-Methode](icorpublishprocess-getprocessid-method.md)|Ruft den Betriebssystem Bezeichner für den Prozess ab, auf den von diesem `ICorPublishProcess`verwiesen wird.|  
|[IsManaged-Methode](icorpublishprocess-ismanaged-method.md)|Ruft einen Wert ab, der angibt, ob der Prozess, auf den dieser `ICorPublishProcess` verweist, bekanntermaßen verwalteten Code ausgeführt.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](corpubpublish-coclass.md)
