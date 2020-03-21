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
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175810"
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType-Methode
Erstellt die Metadatensignatur einer Typdefinition, gibt ein `mdTypeDef` Token für diesen Typ zurück und gibt an, `tdEncloser` dass der definierte Typ ein Member des Typs ist, auf den der Parameter verweist.  
  
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
 [in] Der Name des Typs in Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` Attribute. Dies ist eine `CorTypeAttr` Bitmaske von Werten.  
  
 `tkExtends`  
 [in] Das Token der Basisklasse. Dies ist `mdTypeDef` entweder `mdTypeRef` ein oder ein Token.  
  
 `rtkImplements`[]  
 [in] Ein Array von Token, die die Schnittstellen angeben, die diese Klasse oder Schnittstelle implementiert.  
  
 `tdEncloser`  
 [in] Das Token des einschließenden Typs. Das letzte Element des `mdTokenNil`Arrays muss .  
  
 `ptd`  
 [out] Das `mdTypeDef` token zugewiesen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
