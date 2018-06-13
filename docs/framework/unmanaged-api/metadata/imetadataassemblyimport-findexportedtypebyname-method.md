---
title: IMetaDataAssemblyImport::FindExportedTypeByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 048c7234fcb2592ea0dade135a32341a6e0f404f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444918"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>IMetaDataAssemblyImport::FindExportedTypeByName-Methode
Ruft einen Zeiger auf einem exportierten Typ erhält den Namen und den einschließenden Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szName`  
 [in] Der Name des exportierten Typs.  
  
 `mdtExportedType`  
 [in] Das Metadatentoken für die einschließende Klasse des exportierten Typs. Dieser Wert ist `mdExportedTypeNil` , wenn der angeforderte exportiert ist keines geschachtelten Typs.  
  
 `ptkExportedType`  
 [out] Ein Zeiger auf die `mdExportedType` Token, das den exportierten Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `FindExportedTypeByName` Methode verwendet die Standardregeln, die von der common Language Runtime zum Auflösen von verweisen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
