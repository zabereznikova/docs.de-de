---
title: SetAssemblyFile2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
ms.openlocfilehash: 4f710ef9741869a2b4fd8473ed3ecf379cfcc56d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445587"
---
# <a name="setassemblyfile2-method"></a>SetAssemblyFile2-Methode
Legt den Namen der Optionen und für eine neue Assembly fest. Rufen Sie diese Methode nicht auf, wenn Sie ungebundene Module entwickeln.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszFilename`  
 Der Name der Manifest-Datei.  
  
 `pEmitter`  
 [IMetaDataEmit2 Schnittstellen](../metadata/imetadataemit2-interface.md) Schnittstelle für diese Datei.  
  
 `afFlags`  
 Optionen, die durch die [AssemblyFlags-Enumeration](../metadata/assemblyflags-enumeration.md)dargestellt werden.  
  
 `pAssemblyID`  
 Empfängt eine eindeutige ID für die Assembly, die erstellt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
