---
title: ImportFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: cda6d90865f8ad2b9d565f6a6378c35b03c65bf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446995"
---
# <a name="importfile-method"></a>ImportFile-Methode
Importiert Assemblys und ungebundene Module.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszFilename`  
 Der voll qualifizierte Name der zu importierenden Datei.  
  
 `pszTargetName`  
 Optionaler Name der Ausgabedatei, die verwendet werden kann, um die Datei umzubenennen, wenn Sie mit der Assembly verknüpft ist.  
  
 `fSmartImport`  
 TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.  
  
 `pImportToken`  
 Zeiger auf das Token, in dem eine eindeutige Datei-ID gespeichert wird. Bei der Datei kann es sich um eine Assembly oder eine Datei handeln.  
  
 `ppAssemblyScope`  
 Empfängt einen Zeiger auf die [IMetaDataAssemblyImport-Schnittstelle](../metadata/imetadataassemblyimport-interface.md). Kann NULL sein, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Zeiger auf die Anzahl der importierten Dateien und/oder Bereiche.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
