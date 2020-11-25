---
title: AddFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 53ca4005f5681cfc5d550301d8aad1406aceb3a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717200"
---
# <a name="addfile-method"></a>AddFile-Methode

Fügt der Assembly Dateien hinzu. Kann auch verwendet werden, um ungebundene Module zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `AssemblyID`  
 Eindeutige ID der Assembly, die erweitert werden soll.  
  
 `pszFilename`  
 Der voll qualifizierte Name der hinzu zufügenden Datei.  
  
 `dwFlags`  
 Com+-FileDef-Flags, z `ffContainsNoMetaData` `ffWriteable` . b. und. `dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.  
  
 `pEmitter`  
 [IMetaDataEmit-Schnittstellen](../metadata/imetadataemit-interface.md) Schnittstelle, die zum Ausgeben von Metadaten verwendet werden soll, falls erforderlich.  
  
 `pFileToken`  
 Ein Zeiger auf den Speicherort, an dem die eindeutige ID der hinzugefügten Datei gespeichert wird.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
