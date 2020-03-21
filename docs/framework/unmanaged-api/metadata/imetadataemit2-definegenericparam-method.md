---
title: IMetaDataEmit2::DefineGenericParam-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177452"
---
# <a name="imetadataemit2definegenericparam-method"></a>IMetaDataEmit2::DefineGenericParam-Methode
Erstellt eine Definition für einen generischen Typparameter und ruft ein Token für diesen generischen Typparameter ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 [in] Ein `mdTypeDef` `mdMethodDef` oder ein Token, das die Methode oder den Konstruktor darstellt, für die ein generischer Parameter definiert werden soll.  
  
 `ulParamSeq`  
 [in] Der Index des generischen Parameters.  
  
 `dwParamFlags`  
 [in] Ein Wert der [CorGenericParamAttr-Enumeration,](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) der den Typ für den generischen Parameter beschreibt.  
  
 `szname`  
 [in] Der Name des Parameters.  
  
 `reserved`  
 [in] Dieser Parameter ist für zukünftige Erweiterbarkeit reserviert.  
  
 `rtkConstraints`  
 [in] Ein Null-Termin-Array von Typeinschränkungen. Arraymember müssen `mdTypeDef`ein `mdTypeRef`, `mdTypeSpec` oder Metadatentoken sein.  
  
 `pgp`  
 [out] Ein Token, das den generischen Parameter darstellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
