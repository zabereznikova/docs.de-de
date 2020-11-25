---
title: SetAssemblyFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732644"
---
# <a name="setassemblyfile-method"></a>SetAssemblyFile-Methode

Weist den Namen der Assembly zu, die erstellt werden soll. Nicht für die Verwendung beim Erstellen von ungebundenen Modulen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `pszFilename`  
 Der voll qualifizierte Name der Manifest-Datei.  
  
 `pEmitter`  
 Zeiger auf die [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) -Schnittstelle.  
  
 `afFlags`  
 Flags, wie in [AssemblyFlags-Enumeration](../metadata/assemblyflags-enumeration.md)definiert.  
  
 `pAssemblyID`  
 Zeiger auf die ID der resultierenden Assembly.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
