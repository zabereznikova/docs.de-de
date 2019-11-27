---
title: IMetaDataEmit::DefineImportType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 5b4b0682b2bddff96cb3d720900ed3aa39f06f9d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431850"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType-Methode
Erstellt einen Verweis auf den angegebenen Typ, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAssemImport`  
 in Eine [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus der der Zieltyp importiert wird.  
  
 `pbHashValue`  
 in Ein Array, das den Hash für die durch `pAssemImport`angegebene Assembly enthält.  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 in Eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zieltyp importiert wird.  
  
 `tdImport`  
 in Ein `mdTypeDef` Token, das den Zieltyp angibt.  
  
 `pAssemEmit`  
 in Eine [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in die der Zieltyp importiert wird.  
  
 `ptr`  
 vorgenommen Das `mdTypeRef` Token, das im aktuellen Gültigkeitsbereich für den Typverweis definiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Vor dem Aufrufen der [IMetaDataEmit::D efineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) -Methode können Sie die `DefineImportType`-Methode verwenden, um einen Typverweis im aktuellen Gültigkeitsbereich für die übergeordnete Klasse oder übergeordnete Schnittstelle des Elements zu erstellen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
