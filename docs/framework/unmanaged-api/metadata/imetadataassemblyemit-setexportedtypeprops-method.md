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
ms.openlocfilehash: 076d027945dc27942e4b0989e14e86d829f76679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713485"
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
 in Das Metadatentoken, das die `ExportedType` zu ändernde Metadatenstruktur angibt.  
  
 `tkImplementation`  
 in Das Token vom Typ `File` , `AssemblyRef` oder, `ExportedType` das angibt, wie dieser Typ implementiert wird.  
  
 `tkTypeDef`  
 in Das `TypeDef` Token, auf das in der Codedatei verwiesen wird.  
  
 `dwExportedTypeFlags`  
 in Eine bitweise Kombination von-Werten, die Attribute des Typs angeben.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie zum Erstellen einer `ExportedType` Metadatenstruktur die [IMetaDataAssemblyEmit::D efineexportedtype](imetadataassemblyemit-defineexportedtype-method.md) -Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
