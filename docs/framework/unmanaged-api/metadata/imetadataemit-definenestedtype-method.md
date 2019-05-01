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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebd4e9beca315ef8284c915800afec6bdb78c78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044004"
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType-Methode
Erstellt die Metadatensignatur einer Typdefinition ist, wird ein `mdTypeDef` ein Sicherheitstoken für diesen Typ, und gibt an, dass der definierte Typ ein Member des Typs verwiesen wird, durch die `tdEncloser` Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Der Name des Typs im Unicode-Format.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` Attribute. Dies ist eine Bitmaske der `CorTypeAttr` Werte.  
  
 `tkExtends`  
 [in] Das Token der Basisklasse. Dies ist entweder ein `mdTypeDef` oder `mdTypeRef` token.  
  
 `rtkImplements`[]  
 [in] Ein Array von Token, die die Schnittstellen anzugeben, die diese Klasse oder Schnittstelle implementiert.  
  
 `tdEncloser`  
 [in] Das Token des einschließenden Typs. Das letzte Element des Arrays muss `mdTokenNil`.  
  
 `ptd`  
 [out] Die `mdTypeDef` zugewiesene Token.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
