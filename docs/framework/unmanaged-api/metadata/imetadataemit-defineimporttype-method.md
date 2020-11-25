---
title: IMetaDataEmit::DefineImportType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 94ce4443be210fdfeb1bab197c3e603255e1cc4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723245"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType-Methode

Erstellt einen Verweis auf den angegebenen Typ, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pAssemImport`  
 in Eine [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus der der Zieltyp importiert wird.  
  
 `pbHashValue`  
 in Ein Array, das den Hash für die durch angegebene Assembly enthält `pAssemImport` .  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 in Eine [IMetaDataImport](imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zieltyp importiert wird.  
  
 `tdImport`  
 in Ein `mdTypeDef` Token, das den Zieltyp angibt.  
  
 `pAssemEmit`  
 in Eine [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in die der Zieltyp importiert wird.  
  
 `ptr`  
 vorgenommen Das `mdTypeRef` Token, das im aktuellen Gültigkeitsbereich für den Typverweis definiert wird.  
  
## <a name="remarks"></a>Hinweise  

 Vor dem Aufrufen der [IMetaDataEmit::D efineimportmember](imetadataemit-defineimportmember-method.md) -Methode können Sie mit der `DefineImportType` -Methode einen Typverweis im aktuellen Gültigkeitsbereich für die übergeordnete Klasse oder übergeordnete Schnittstelle des Members erstellen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
