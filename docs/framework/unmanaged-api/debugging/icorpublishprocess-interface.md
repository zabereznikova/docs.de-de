---
title: ICorPublishProcess-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess
helpviewer_keywords: ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cb62da277ff13bea33969bb9c728cac5d5a15554
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess-Schnittstelle
Stellt Methoden, die Zugriff auf Informationen, die angezeigt werden, zu einem Prozess bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumAppDomains-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|Ruft eine [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Anwendungsdomänen im Prozess verwiesen, die von diesem enthält `ICorPublishProcess`.|  
|[GetDisplayName-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess, auf die verwiesen wird von diesem `ICorPublishProcess`.|  
|[GetProcessID-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|Ruft den Bezeichner des Betriebssystems für den Prozess, auf die verwiesen wird von diesem `ICorPublishProcess`.|  
|[IsManaged-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|Ruft einen Wert, der angibt, ob dies der Prozess verweist `ICorPublishProcess` ist bekanntermaßen mit verwalteten Code ausgeführt werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [CorpubPublish-Co-Klasse](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
