---
title: IHostFilter::MarkToken-Methode
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432241"
---
# <a name="ihostfiltermarktoken-method"></a>IHostFilter::MarkToken-Methode
Gibt an, dass das angegebene Metadatentoken verarbeitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 in Das zu verarbeitende Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  
 In der Regel möchten Sie, dass ein Token verarbeitet wird, wenn es sich im Metadatenbereich befindet. Die `MarkToken`-Methode wird über die [IMetaDataEmit:: lthandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) -Methode an die metadatenengine übermittelt.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IHostFilter-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
