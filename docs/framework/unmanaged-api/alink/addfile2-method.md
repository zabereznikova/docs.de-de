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
ms.openlocfilehash: 8dadf9ec8f896b03e4918b21f5153c1b747010fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446665"
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
 Com+ `FileDef` Flags wie `ffContainsNoMetaData` und `ffWriteable`. `dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.  
  
 `pEmitter`  
 Schnittstelle zur [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) -Schnittstelle.  
  
 `pFileToken`  
 Empfängt die ID für die Datei, die hinzugefügt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
