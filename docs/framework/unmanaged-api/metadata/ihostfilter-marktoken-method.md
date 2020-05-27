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
ms.openlocfilehash: 11529ce896f265f2b200fa6e511d4b913e9147c8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008221"
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
 In der Regel möchten Sie, dass ein Token verarbeitet wird, wenn es sich im Metadatenbereich befindet. Die- `MarkToken` Methode wird über die [IMetaDataEmit:: lthandler](imetadataemit-sethandler-method.md) -Methode an die metadatenengine übermittelt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IHostFilter-Schnittstelle](ihostfilter-interface.md)
