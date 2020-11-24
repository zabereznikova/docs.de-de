---
title: IMetaDataEmit::SetCustomAttributeValue-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: c4ea325a755ed05eed378d9201068de31ca8114f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681579"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a>IMetaDataEmit::SetCustomAttributeValue-Methode

Legt den Wert eines benutzerdefinierten Attributs fest, das durch einen vorherigen [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md)definiert ist, oder aktualisiert diesen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pcv`  
 in Das Token des benutzerdefinierten Ziel Attributs.  
  
 `pCustomAttribute`  
 in Ein Zeiger auf das Array, das das benutzerdefinierte Attribut enthält.  
  
 `cbCustomAttribute`  
 in Die Größe (in Bytes) des benutzerdefinierten Attributs.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
