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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8cd086a86d104fdfebf1a8298a22b795cb2389b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782647"
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs-Methode
Ruft einen Enumerator für ein Array von MethodSpec-Token mit dem angegebenen MethodDef oder MemberRef verknüpften token.  
  
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
 [in] Das MemberRef oder MethodDef-Token, das die Methode darstellt, deren MethodSpec-Token sind, aufgelistet werden sollen. Wenn der Wert des `tk` ist 0 (null), alle MethodSpec-Token im Bereich, werden aufgezählt.  
  
 `rMethodSpecs`  
 [out] Das Array von aufzulistenden MethodSpec-Token.  
  
 `cMax`  
 [in] Die angeforderte maximale Anzahl von Token in platzieren `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 [out] Die zurückgegebene Anzahl von Token in platziert `rMethodSpecs`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum` enthält keine Memberelemente. In diesem Fall `pcMethodSpecs` auf 0 (null) festgelegt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
