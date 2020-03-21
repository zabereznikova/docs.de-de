---
title: IMetaDataImport2::EnumMethodSpecs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177174"
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs-Methode
Ruft einen Enumerator für ein Array von MethodSpec-Token ab, die dem angegebenen MethodDef- oder MemberRef-Token zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator für `rMethodSpecs`.  
  
 `tk`  
 [in] Das MemberRef- oder MethodDef-Token, das die Methode darstellt, deren MethodSpec-Token aufgezählt werden sollen. Wenn der `tk` Wert von 0 (Null) ist, werden alle MethodSpec-Token im Bereich aufgezählt.  
  
 `rMethodSpecs`  
 [out] Das Array von MethodSpec-Token, die aufgezählt werden sollen.  
  
 `cMax`  
 [in] Die angeforderte maximale Anzahl von `rMethodSpecs`Token, die in platziert werden sollen.  
  
 `pcMethodSpecs`  
 [out] Die zurückgegebene Anzahl von `rMethodSpecs`Token, die in platziert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|`phEnum`hat keine Elementelemente. In diesem `pcMethodSpecs` Fall ist auf 0 (Null) gesetzt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
