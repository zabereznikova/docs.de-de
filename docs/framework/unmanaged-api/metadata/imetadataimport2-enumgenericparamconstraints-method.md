---
title: IMetaDataImport2::EnumGenericParamConstraints-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7a51d1ddf7a5a65ce8713161c53c1c54a5d8861
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617693"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a>IMetaDataImport2::EnumGenericParamConstraints-Methode
Ruft einen Enumerator für ein Array von generischen Parameter-Einschränkungen, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `tk`  
 [in]   Ein Token, das den generischen Parameter darstellt, deren Einschränkungen aufgelistet werden sollen.  
  
 `rGenericParamConstraints`  
 [out] Das Array von Einschränkungen für generische Typparameter aufgelistet werden.  
  
 `cMax`  
 [in]   Die angeforderte maximale Anzahl von Token in platzieren `rGenericParamConstraints`.  
  
 `pcGenericParamConstraints`  
 [out] Ein Zeiger auf die Anzahl der Token in platziert `rGenericParamConstraints`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum` enthält keine Memberelemente. In diesem Fall `pcGenericParameterConstraints` auf 0 (null) festgelegt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
