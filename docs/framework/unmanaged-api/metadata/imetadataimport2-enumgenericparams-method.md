---
title: IMetaDataImport2::EnumGenericParams-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumGenericParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da7a77bd1a758e4bb7fad3fcd15621176abc92a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2enumgenericparams-method"></a>IMetaDataImport2::EnumGenericParams-Methode
Ruft einen Enumerator für ein Array von generischen Parameter-Token mit dem angegebenen TypeDef- oder MethodDef verknüpften token.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `tk`  
 [in] Die TypeDef oder MethodDef-Token, dessen generischen Parametern werden aufgelistet werden sollen.  
  
 `rGenericParams`  
 [out] Das Array von generischen Parametern aufgelistet werden.  
  
 `cMax`  
 [in] Die angeforderte maximale Anzahl von Token zu versehen `rGenericParams`.  
  
 `pcGenericParams`  
 [out] Die zurückgegebene Anzahl von Token in platziert `rGenericParams`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum`verfügt über keine Memberelemente. In diesem Fall `pcGenericParams` auf 0 (null) festgelegt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
