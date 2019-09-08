---
title: ImportFileEx-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777114"
---
# <a name="importfileex-method"></a>ImportFileEx-Methode
Importiert die angegebener Assembly oder das nicht gebundene Modul.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszFilename`  
 Der voll qualifizierte Name der Datei, aus der importiert werden soll.  
  
 `pszTargetName`  
 Optionaler Name der Zieldatei.  
  
 `fSmartImport`  
 TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.  
  
 `dwOpenFlags`  
 Flags, die an die [OpenScope-Methode](../metadata/imetadatadispenser-openscope-method.md)weitergegeben werden sollen.  
  
 `pImportToken`  
 Empfängt die ID der Datei, die importiert wird.  
  
 `ppAssemblyScope`  
 Empfängt assemblyimportierungsbereich [IMetaDataAssemblyImport Schnittstellen](../metadata/imetadataassemblyimport-interface.md) Schnittstelle. Wird auf NULL festgelegt, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Empfängt die Anzahl importierter Dateien und/oder Bereiche.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
