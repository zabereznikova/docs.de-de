---
title: IMetaDataFilter-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4196ff2cb2d4ebc401076f603a8a7fdc9b9c76ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049959"
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
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
