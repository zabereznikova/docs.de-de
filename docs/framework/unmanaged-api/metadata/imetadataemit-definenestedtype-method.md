---
title: IMetaDataEmit::DefineNestedType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719540"
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType-Methode

Erstellt die Metadatensignatur einer Typdefinition, gibt ein `mdTypeDef` Token für diesen Typ zurück und gibt an, dass der definierte Typ ein Member des Typs ist, auf den vom-Parameter verwiesen wird `tdEncloser` .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `szTypeDef`  
 in Der Name des Typs in Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` legt. Dies ist eine Bitmaske von `CorTypeAttr` Werten.  
  
 `tkExtends`  
 in Das Token der Basisklasse. Dabei handelt es sich entweder um ein- `mdTypeDef` oder- `mdTypeRef` Token.  
  
 `rtkImplements`[]  
 in Ein Array von Token, die die Schnittstellen angeben, die von dieser Klasse oder Schnittstelle implementiert werden.  
  
 `tdEncloser`  
 in Das Token des einschließenden Typs. Das letzte Element des Arrays muss sein `mdTokenNil` .  
  
 `ptd`  
 vorgenommen Das `mdTypeDef` zugewiesene Token.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
