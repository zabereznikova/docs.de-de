---
title: IMetaDataEmit::DefineImportType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fee13c88cc39398808ad1ff481e602d63e8f39f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType-Methode
Erstellt einen Verweis auf den angegebenen Typ, der außerhalb des aktuellen Bereichs definiert ist, und ein Token für diesen Verweis definiert.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `pAssemImport`  
 [in] Ein [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle, die die Assembly darstellt, aus dem der Zieltyp importiert wird.  
  
 `pbHashValue`  
 [in] Ein Array, das den Hash für die Assembly gemäß enthält `pAssemImport`.  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 [in] Ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zieltyp importiert wird.  
  
 `tdImport`  
 [in] Ein `mdTypeDef` Token, das den Zieltyp angibt.  
  
 `pAssemEmit`  
 [in] Ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) Schnittstelle, die die Assembly darstellt, in dem der Zieltyp importiert wird.  
  
 `ptr`  
 [out] Die `mdTypeRef` Token, das im aktuellen Bereich für den Typverweis definiert ist.  
  
## <a name="remarks"></a>Hinweise  
 Vor dem Aufruf der [IMetaDataEmit:: DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) -Methode, die Sie verwenden die `DefineImportType` Methode, um einen Typverweis, im aktuellen Bereich, für des Elements übergeordnete Klasse oder Schnittstelle zu erstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
