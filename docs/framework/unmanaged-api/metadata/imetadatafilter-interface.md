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
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440169"
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter-Schnittstelle
Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[IsTokenMarked-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|Gets a value indicating whether the specified metadata token has been processed.|  
|[MarkToken-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|Sets a value indicating that the specified metadata token has been processed.|  
|[UnmarkAll-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|Removes the processing marks from all the tokens in the current metadata scope.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
