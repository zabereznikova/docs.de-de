---
title: EmbedResource-Methode
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: 24279870e7406de649df56e8aad31252513e95c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446539"
---
# <a name="embedresource-method"></a>EmbedResource-Methode
Declares an embedded resource. This method does not actually embed the resource.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 ID of the assembly.  
  
 `FileToken`  
 File token or assembly ID of file that contains the resource.  
  
 `pszResourceName`  
 Name der Ressource.  
  
 `dwOffset`  
 Offset of resource from RVA.  
  
 `dwFlags`  
 Accessibility flags such as `mrPublic` and `mrPrivate`. These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
## <a name="return-value"></a>Rückgabewert  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>Anforderungen  
 Requires alink.h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
