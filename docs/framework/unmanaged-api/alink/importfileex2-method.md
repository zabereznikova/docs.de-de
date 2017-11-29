---
title: ImportFileEx2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx2
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx2
helpviewer_keywords: ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c2416a630f9bd763d4d4d31170cc606b160bb854
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex2-method"></a>ImportFileEx2-Methode
Imports-Assemblys und ungebundenen Modulen. Diese Methode entspricht [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), aber funktioniert auch, wenn die zu importierende Datei auf dem Datenträger nicht vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszFilename`  
 Name der zu importierenden Datei.  
  
 `pszTargetName`  
 Optionale Name der Zieldatei.  
  
 `pAssemblyScopeIn`  
 Optionalen Importgültigkeitsbereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.  
  
 `fSmartImport`  
 Bei "true", ImportTypes verwendet wird, andernfalls importieren muss manuell durchgeführt werden.  
  
 `dwOpenFlags`  
 Flags an, zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Empfängt die eindeutige ID für die Assembly oder Datei.  
  
 `ppAssemblyScope`  
 Empfängt Import assemblygültigkeitsbereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle. NULL kann sein, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Empfängt die Anzahl der Dateien und/oder Bereiche nicht importiert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Siehe auch  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
