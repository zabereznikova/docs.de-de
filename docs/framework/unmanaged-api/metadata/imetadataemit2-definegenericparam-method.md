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
ms.openlocfilehash: 3898b095809e2b84f71aba2036f4d7a294dfdf6a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444655"
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
 in Ein `mdTypeDef` oder `mdMethodDef` Token, das die Methode oder den Konstruktor darstellt, für die ein generischer Parameter definiert werden soll.  
  
 `ulParamSeq`  
 in Der Index des generischen Parameters.  
  
 `dwParamFlags`  
 in Ein Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.  
  
 `szname`  
 in Der Name des Parameters.  
  
 `reserved`  
 in Dieser Parameter ist für die zukünftige Erweiterbarkeit reserviert.  
  
 `rtkConstraints`  
 in Ein mit Null endendes Array von Typeinschränkungen. Array Elemente müssen ein `mdTypeDef`-, `mdTypeRef`-oder `mdTypeSpec` Metadatentoken sein.  
  
 `pgp`  
 vorgenommen Ein Token, das den generischen Parameter darstellt.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
