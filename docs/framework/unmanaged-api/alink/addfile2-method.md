---
title: AddFile2-Methode
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777522"
---
# <a name="addfile2-method"></a>AddFile2-Methode
Fügt der Assembly Dateien hinzu. Kann auch verwendet werden, um ungebundene Module zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 ID für die Assembly, der die Datei hinzugefügt wird.  
  
 `pszFilename`  
 Der Name der hinzu zufügenden Datei.  
  
 `dwFlags`  
 Com+ `FileDef` `ffContainsNoMetaData` -Flags, wie `ffWriteable`z. b. und. `dwFlags`wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.  
  
 `pEmitter`  
 Schnittstelle zur [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) -Schnittstelle.  
  
 `pFileToken`  
 Empfängt die ID für die Datei, die hinzugefügt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
