---
title: LinkResource-Methode
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 9e91d990a8f23335248043c59eb210e8c4155e3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445629"
---
# <a name="linkresource-method"></a>LinkResource-Methode
Verknüpfungen in einer Ressource.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly.  
  
 `pszFileName`  
 Der Name der Datei.  
  
 `pszNewLocation`  
 Optionaler neuer Dateiname. Wenn der Wert nicht NULL ist, werden `pszFileName` in pszNewLocation kopiert.  
  
 `pszResourceName`  
 Name der Ressource.  
  
 `dwFlags`  
 Barrierefreiheits Flags wie `mrPublic` und `mrPrivate`. Dieser Parameter kann an die [DefineManifestResource-Methode](../metadata/imetadataassemblyemit-definemanifestresource-method.md)übergeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
