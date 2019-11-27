---
title: AddImport-Methode
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
ms.openlocfilehash: 52e52ac62e2dcfeb182da3014a863409f640274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446657"
---
# <a name="addimport-method"></a>AddImport-Methode
Fügt der Assembly Importe hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Eindeutige ID der Assembly, die erweitert werden soll.  
  
 `ImportToken`  
 Die eindeutige ID, die von der [ImportFile-Methode](importfile-method.md)abgerufen wird, der zu importierenden Datei.  
  
 `dwFlags`  
 Com+-FileDef-Flags wie `ffContainsNoMetaData` und `ffWriteable`. `dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.  
  
 `pFileToken`  
 Zeiger auf das Token, das die ID für die resultierende Datei empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
