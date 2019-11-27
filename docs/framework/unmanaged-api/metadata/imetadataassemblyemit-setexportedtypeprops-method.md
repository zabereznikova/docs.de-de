---
title: IMetaDataAssemblyEmit::SetExportedTypeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: ae682c354a7a5188611b103008a3e18f8d821260
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431942"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a>IMetaDataAssemblyEmit::SetExportedTypeProps-Methode
Ändert die angegebene `ExportedType`-Metadatenstruktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ct`  
 in Das Metadatentoken, das die zu ändernde `ExportedType` Metadatenstruktur angibt.  
  
 `tkImplementation`  
 in Das Token vom Typ `File`, `AssemblyRef`oder `ExportedType`, das angibt, wie dieser Typ implementiert wird.  
  
 `tkTypeDef`  
 in Das `TypeDef` Token, auf das in der Codedatei verwiesen wird.  
  
 `dwExportedTypeFlags`  
 in Eine bitweise Kombination von-Werten, die Attribute des Typs angeben.  
  
## <a name="remarks"></a>Hinweise  
 Um eine `ExportedType` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::D efineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) -Methode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
