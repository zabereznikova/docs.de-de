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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9debf041a26af128dea3cde214630f5a95eac71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090656"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType-Methode
Erstellt einen Verweis auf den angegebenen Typ, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Ein [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus der der Zieltyp importiert wird.  
  
 `pbHashValue`  
 [in] Ein Array, das den Hash für die Assembly, die anhand des enthält `pAssemImport`.  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 [in] Ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus der der Zieltyp importiert wird.  
  
 `tdImport`  
 [in] Ein `mdTypeDef` Token, das den Zieltyp angibt.  
  
 `pAssemEmit`  
 [in] Ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in die der Zieltyp importiert wird.  
  
 `ptr`  
 [out] Die `mdTypeRef` Token, das im aktuellen Bereich für den Typverweis definiert ist.  
  
## <a name="remarks"></a>Hinweise  
 Vor dem Aufrufen der [IMetaDataEmit:: DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) -Methode, die Sie verwenden die `DefineImportType` Methode, um einen Typverweis, im aktuellen Bereich, für des Members übergeordnete Klasse oder Schnittstelle zu erstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
