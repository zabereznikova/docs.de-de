---
title: IMetaDataImport2::EnumGenericParams-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 093e3edf0a3c06222ebc56a4876fca08d1b7578f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490727"
---
# <a name="imetadataimport2enumgenericparams-method"></a>IMetaDataImport2::EnumGenericParams-Methode
Ruft einen Enumerator für ein Array von generischen Parameter Token ab, die dem angegebenen TypeDef-oder MethodDef-Token zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `tk`  
 in Das TypeDef-oder MethodDef-Token, dessen generische Parameter aufgezählt werden sollen.  
  
 `rGenericParams`  
 vorgenommen Das Array von generischen Parametern, die aufgelistet werden sollen.  
  
 `cMax`  
 in Die angeforderte maximale Anzahl von Token, die in platziert werden sollen `rGenericParams` .  
  
 `pcGenericParams`  
 vorgenommen Die zurückgegebene Anzahl von Token, die in platziert werden `rGenericParams` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum`hat keine Member-Elemente. In diesem Fall `pcGenericParams` wird auf 0 (null) festgelegt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
