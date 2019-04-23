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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182961"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess-Schnittstelle
Bietet Methoden, die Informationen, die angezeigt wird, werden zu einem Prozess zugreifen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumAppDomains-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|Ruft eine [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Anwendungsdomänen im Prozess auf die dieses enthält `ICorPublishProcess`.|  
|[GetDisplayName-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess, der auf die dieses `ICorPublishProcess`.|  
|[GetProcessID-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|Ruft den Bezeichner für den Prozess, der auf die dieses `ICorPublishProcess`.|  
|[IsManaged-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|Ruft einen Wert, der angibt, ob von dieser vom Prozess verwiesen `ICorPublishProcess` ist bekannt, dass verwalteten Code ausgeführt werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
