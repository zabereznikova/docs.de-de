---
title: IMetaDataAssemblyEmit::SetManifestResourceProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
ms.openlocfilehash: c46a3bc34ba7efa760e50416e9a6c39779727813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708919"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>IMetaDataAssemblyEmit::SetManifestResourceProps-Methode

Ändert die angegebene `ManifestResource`-Metadatenstruktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mr`  
 in Das Token, das die `ManifestResource` zu ändernde Metadatenstruktur angibt.  
  
 `tkImplementation`  
 in Das Token vom Typ `File` oder, `AssemblyRef` das dem Ressourcenanbieter zugeordnet wird.  
  
 `dwOffset`  
 in Der Offset zum Anfang der Ressource innerhalb der Datei.  
  
 `dwResourceFlags`  
 in Eine bitweise Kombination von Flagwerten, die die Attribute der Ressource angeben.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie zum Erstellen einer `ManifestResource` Metadatenstruktur die [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) -Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
