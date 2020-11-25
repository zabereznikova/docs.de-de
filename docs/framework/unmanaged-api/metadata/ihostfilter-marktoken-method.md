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
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718227"
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
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IHostFilter-Schnittstelle](ihostfilter-interface.md)
