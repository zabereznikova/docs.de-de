---
title: IMetaDataImport2::GetGenericParamConstraintProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1d76dcd581b54d54d6b44505e09476993b2930c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446816"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a>IMetaDataImport2::GetGenericParamConstraintProps-Methode
Ruft die Einschränkung des generischen Parameters, durch die angegebene Einschränkung-Token dargestellt wird zugeordneten Metadaten ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `gpc`  
 [in] Das Token für die Einschränkung der generischen Parameter für die die Metadaten zurückgegeben werden sollen.  
  
 `ptGenericParam`  
 [out] Ein Zeiger auf das Token, das den generischen Parameter darstellt, der eingeschränkt wird.  
  
 `ptkConstraintType`  
 [out] Ein Zeiger auf eine TypeDef, TypeRef-Token oder TypeSpec-Token, die eine Einschränkung auf darstellt `ptGenericParam`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
