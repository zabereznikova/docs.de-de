---
title: IMetaDataEmit::DefineNestedType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineNestedType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf0357275b0ad2dd7d57a3b3f07e17dc3e38e1a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType-Methode
Erstellt die Metadatensignatur einer Typdefinition ist, wird ein `mdTypeDef` token für diesen Typ und gibt an, dass der definierte Typ ein Member des Typs verweist die `tdEncloser` Parameter.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `szTypeDef`  
 [in] Der Name des Typs im Unicode-Format.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` Attribute. Dies ist eine Bitmaske der `CorTypeAttr` Werte.  
  
 `tkExtends`  
 [in] Das Token der Basisklasse. Dies liegt entweder an einem `mdTypeDef` oder ein `mdTypeRef` token.  
  
 `rtkImplements`[]  
 [in] Ein Array von Token, die die Schnittstellen anzugeben, die diese Klasse oder Schnittstelle implementiert.  
  
 `tdEncloser`  
 [in] Das Token des einschließenden Typs. Das letzte Element des Arrays muss `mdTokenNil`.  
  
 `ptd`  
 [out] Die `mdTypeDef` Token zugewiesen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
