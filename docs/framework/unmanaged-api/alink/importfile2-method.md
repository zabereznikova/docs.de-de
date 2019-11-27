---
title: ImportFile2-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
ms.openlocfilehash: 17f158167d4075783d1aa594fb61cc9e28d30dd7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446983"
---
# <a name="importfile2-method"></a>ImportFile2-Methode
Importiert Assemblys und ungebundene Module. Diese Methode verhält sich wie die [ImportFile-Methode](importfile-method.md), funktioniert aber auch dann, wenn die zu importierende Datei nicht auf dem Datenträger vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszFilename`  
 Der Name der zu importierenden Datei.  
  
 `pszTargetName`  
 Optionaler Name der Ausgabedatei, die verwendet werden kann, um die Datei umzubenennen, wenn Sie mit der Assembly verknüpft ist.  
  
 `pAssemblyScopeIn`  
 Optionaler Bereich der [IMetaDataAssemblyImport-Schnittstelle](../metadata/imetadataassemblyimport-interface.md) .  
  
 `fSmartImport`  
 TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.  
  
 `pImportToken`  
 Empfängt die ID für die Datei oder Assembly.  
  
 `ppAssemblyScope`  
 Empfängt die Schnittstelle der [IMetaDataAssemblyImport-Schnittstelle](../metadata/imetadataassemblyimport-interface.md) . NULL, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Empfängt die gefundenen Dateien und/oder Bereiche, die importiert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
