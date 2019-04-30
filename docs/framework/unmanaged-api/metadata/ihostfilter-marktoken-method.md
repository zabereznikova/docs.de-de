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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3214a21dda27fda01054e96400997b15d11f71b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905423"
---
# <a name="ihostfiltermarktoken-method"></a>IHostFilter::MarkToken-Methode
Gibt an, dass das angegebene Metadatentoken verarbeitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 [in] Das Metadatentoken verarbeitet werden.  
  
## <a name="remarks"></a>Hinweise  
 In der Regel sollten Sie ein Token verarbeitet werden, wenn sie im Metadatenbereich befindet. Die `MarkToken` Methode übergeben wird, um die Metadaten-Engine über die [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IHostFilter-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
