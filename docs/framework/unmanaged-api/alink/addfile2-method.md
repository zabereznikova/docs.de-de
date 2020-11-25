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
ms.openlocfilehash: cff6707496c7d9657796deb8bf6fa9165ff295a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717083"
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
 Com+ `FileDef` -Flags, wie z `ffContainsNoMetaData` `ffWriteable` . b. und. `dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.  
  
 `pEmitter`  
 Schnittstelle zur [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) -Schnittstelle.  
  
 `pFileToken`  
 Empfängt die ID für die Datei, die hinzugefügt wird.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [ALink-API](index.md)
