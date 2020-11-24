---
title: IMetaDataEmit::SetParent-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: cef817b52718acfbc4360e9d3742a5a78abd3afe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675047"
---
# <a name="imetadataemitsetparent-method"></a>IMetaDataEmit::SetParent-Methode

Legt fest, dass der angegebene Member, wie durch einen vorherigen-Befehl von [IMetaDataEmit::D efinemembership Ref](imetadataemit-definememberref-method.md)definiert, ein Member des angegebenen Typs ist, wie durch einen vorherigen-Befehl von [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md)definiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mr`  
 in Das `mdMemberRef` Token, das ein neues übergeordnetes Element empfangen soll.  
  
 `tk`  
 in Der `mdToken` für das neue übergeordnete Element.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
