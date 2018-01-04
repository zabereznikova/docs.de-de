---
title: IMetaDataFilter-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter
helpviewer_keywords: IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0918802a146940fb7579279e56f752bd114c746c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter-Schnittstelle
Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[IsTokenMarked-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|Ruft einen Wert, der angibt, ob das angegebene Metadatentoken verarbeitet wurde.|  
|[MarkToken-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|Legt einen Wert, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.|  
|[UnmarkAll-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|Entfernt die Markierungen für die Verarbeitung von allen Token im aktuellen Metadatenbereich.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
