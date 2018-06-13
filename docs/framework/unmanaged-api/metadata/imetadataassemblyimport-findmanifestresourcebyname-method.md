---
title: IMetaDataAssemblyImport::FindManifestResourceByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9afc2ecc34131f62f1f8e8e86ca73f8b8b0126b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443511"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a>IMetaDataAssemblyImport::FindManifestResourceByName-Methode
Ruft einen Zeiger auf die Manifestressource mit dem angegebenen Namen ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a>Parameter  
 `szName`  
 [in] Der Name der Ressource.  
  
 `ptkManifestResource`  
 [out] Das Array zum Speichern der `mdManifestResource` Metadatentoken, von denen jedes eine Manifestressource darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `FindManifestResourceByName` Methode verwendet die Standardregeln, die von der common Language Runtime zum Auflösen von verweisen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
