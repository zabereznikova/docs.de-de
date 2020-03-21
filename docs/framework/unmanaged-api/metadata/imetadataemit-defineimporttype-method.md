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
ms.openlocfilehash: 6825a5198976cc7ab2c04ebd6e782418dcf4a8f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177680"
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
 [in] Eine [IMetaDataAssemblyImport-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) die die Assembly darstellt, aus der der Zieltyp importiert wird.  
  
 `pbHashValue`  
 [in] Ein Array, das den Hash `pAssemImport`für die assembly enthält, die von angegeben wird.  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 [in] Eine [IMetaDataImport-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) die den Metadatenbereich darstellt, aus dem der Zieltyp importiert wird.  
  
 `tdImport`  
 [in] Ein `mdTypeDef` Token, das den Zieltyp angibt.  
  
 `pAssemEmit`  
 [in] Eine [IMetaDataAssemblyEmit-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) die die Assembly darstellt, in die der Zieltyp importiert wird.  
  
 `ptr`  
 [out] Das `mdTypeRef` Token, das im aktuellen Bereich für den Typverweis definiert ist.  
  
## <a name="remarks"></a>Bemerkungen  
 Vor dem Aufrufen der [IMetaDataEmit::DefineImportMember-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) können Sie die `DefineImportType` Methode verwenden, um einen Typverweis im aktuellen Bereich für die übergeordnete Klasse oder übergeordnete Schnittstelle des Elements zu erstellen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
