---
title: IMetaDataImport2::EnumMethodSpecs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db1968c73d5a1c6e0687bc86f249c70b6c21712c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs-Methode
Ruft einen Enumerator für ein Array von MethodSpec-Token mit der angegebenen MethodDef oder MemberRef token.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator für `rMethodSpecs`.  
  
 `tk`  
 [in] Das MemberRef oder MethodDef-Token, das die Methode darstellt, deren MethodSpec-Token aufgelistet werden sollen. Wenn der Wert der `tk` ist 0 (null), werden alle MethodSpec-Token im Bereich aufgezählt werden.  
  
 `rMethodSpecs`  
 [out] Das Array von aufzulistenden MethodSpec-Token.  
  
 `cMax`  
 [in] Die angeforderte maximale Anzahl von Token zu versehen `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 [out] Die zurückgegebene Anzahl von Token in platziert `rMethodSpecs`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum`verfügt über keine Memberelemente. In diesem Fall `pcMethodSpecs` auf 0 (null) festgelegt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
