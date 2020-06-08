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
ms.openlocfilehash: af226f9317b67b23e03d06614ed5b9c956939c22
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503418"
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
 in   Die angeforderte maximale Anzahl von Token, die in platziert werden sollen `rGenericParamConstraints` .  
  
 `pcGenericParamConstraints`  
 vorgenommen Ein Zeiger auf die Anzahl von Token, die in platziert werden `rGenericParamConstraints` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum`hat keine Member-Elemente. In diesem Fall `pcGenericParameterConstraints` wird auf 0 (null) festgelegt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
