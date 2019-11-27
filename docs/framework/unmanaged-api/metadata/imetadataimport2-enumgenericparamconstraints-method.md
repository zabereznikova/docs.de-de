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
ms.openlocfilehash: d1683965193801dbdee038ab06366178891fd978
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426724"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a>IMetaDataImport2::EnumGenericParamConstraints-Methode
Ruft einen Enumerator für ein Array von generischen Parameter Einschränkungen ab, die dem generischen Parameter zugeordnet sind, der durch das angegebene Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `tk`  
 in   Ein Token, das den generischen Parameter darstellt, dessen Einschränkungen aufgelistet werden sollen.  
  
 `rGenericParamConstraints`  
 vorgenommen Das Array der zu enumerieren generischen Parameter Einschränkungen.  
  
 `cMax`  
 in   Die angeforderte maximale Anzahl von Token, die in `rGenericParamConstraints`platziert werden sollen.  
  
 `pcGenericParamConstraints`  
 vorgenommen Ein Zeiger auf die Anzahl von Token, die in `rGenericParamConstraints`platziert werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum` hat keine Member-Elemente. In diesem Fall wird `pcGenericParameterConstraints` auf 0 (null) festgelegt.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
