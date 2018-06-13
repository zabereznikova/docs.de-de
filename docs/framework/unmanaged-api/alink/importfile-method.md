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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54b0a02af7f22e775e3f9567de79664c9805b4e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400649"
---
# <a name="importfile-method"></a>ImportFile-Methode
Imports-Assemblys und ungebundenen Modulen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszFilename`  
 Vollständig qualifizierte Name des zu importierenden Datei.  
  
 `pszTargetName`  
 Optionale Ausgabedateiname, der verwendet werden kann, um die Datei zu benennen, wie sie in der Assembly verknüpft ist.  
  
 `fSmartImport`  
 Bei "true", ImportTypes verwendet wird, andernfalls importieren muss manuell durchgeführt werden.  
  
 `pImportToken`  
 Ein Zeiger auf das token, wo eine eindeutige Datei-ID gespeichert werden sollen. Die Datei kann es sich um eine Assembly oder eine Datei sein.  
  
 `ppAssemblyScope`  
 Zeiger auf empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). NULL kann sein, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Ein Zeiger auf die Anzahl der Dateien und/oder Bereiche, die importiert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
