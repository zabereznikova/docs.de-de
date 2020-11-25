---
title: IMetaDataEmit::DefineTypeRefByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: b83c868f1a804d4e6f32adffc190ae086aa5e0a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719332"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName-Methode

Ruft ein Metadatentoken für einen Typ ab, der im angegebenen Bereich definiert ist, der außerhalb des aktuellen Gültigkeits Bereichs liegt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a>Parameter  

 `tkResolutionScope`  
 in Das Token, das den Auflösungs Bereich angibt. Die folgenden Tokentypen sind gültig:  
  
- `mdModuleRef`, wenn der Typ in derselben Assembly definiert ist, in der der Aufrufer definiert ist.  
  
- `mdAssemblyRef`, wenn der Typ in einer anderen Assembly als der definiert ist, in der der Aufrufer definiert ist.  
  
- `mdTypeRef`, wenn der Typ ein ein Typ ist.  
  
- `mdModule`, wenn der Typ im gleichen Modul definiert ist, in dem der Aufrufer definiert ist.  
  
- NULL, wenn der Typ Global definiert ist.  
  
 `szName`  
 in Der Name des Zieltyps in Unicode.  
  
 `ptr`  
 vorgenommen Ein Zeiger auf das `mdTypeRef` Token, das dem Typ zugewiesen ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
