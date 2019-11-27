---
title: ImportFileEx2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 7e270dbfc63c03e77cb4b0694296e48c2035b8a6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445692"
---
# <a name="importfileex2-method"></a>ImportFileEx2-Methode
Importiert Assemblys und ungebundene Module. Diese Methode verhält sich wie die [ImportFile-Methode](importfile-method.md), funktioniert aber auch dann, wenn die zu importierende Datei nicht auf dem Datenträger vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="parameters"></a>Parameter  
 `pszFilename`  
 Der Name der zu importierenden Datei.  
  
 `pszTargetName`  
 Optionaler Name der Zieldatei.  
  
 `pAssemblyScopeIn`  
 Optionaler Import Bereich [IMetaDataAssemblyImport Schnittstellen](../metadata/imetadataassemblyimport-interface.md) Schnittstelle.  
  
 `fSmartImport`  
 TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.  
  
 `dwOpenFlags`  
 Flags, die an die [OpenScope-Methode](../metadata/imetadatadispenser-openscope-method.md)weitergegeben werden sollen.  
  
 `pImportToken`  
 Empfängt eine eindeutige ID für die Assembly oder Datei.  
  
 `ppAssemblyScope`  
 Empfängt assemblyimportierungsbereich [IMetaDataAssemblyImport Schnittstellen](../metadata/imetadataassemblyimport-interface.md) Schnittstelle. Kann NULL sein, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Empfängt die Anzahl der importierten Dateien und/oder Bereiche.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
