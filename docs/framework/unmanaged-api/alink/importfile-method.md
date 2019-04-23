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
ms.openlocfilehash: 69e48c6c3179ced167fdc39ae4df859f161727ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077250"
---
# <a name="importfile-method"></a>ImportFile-Methode
Assemblys und ungebundenen Modulen importiert.  
  
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
  
## <a name="parameters"></a>Parameter  
 `pszFilename`  
 Voll gekennzeichnete Name des zu importierenden Datei.  
  
 `pszTargetName`  
 Optionale Ausgabedateinamen, die verwendet werden kann, um die Datei umzubenennen, da sie in der Assembly verknüpft ist.  
  
 `fSmartImport`  
 True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.  
  
 `pImportToken`  
 Zeiger auf das token, wo eine eindeutige Datei-ID gespeichert werden sollen. Die Datei kann es sich um eine Assembly oder eine Datei sein.  
  
 `ppAssemblyScope`  
 Zeiger auf empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). NULL kann sein, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Zeiger auf die Anzahl der Dateien bzw. Bereiche, die importiert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
