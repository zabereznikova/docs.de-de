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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aba11ccd61b65d2a779b39db8e0e082cf4d4015b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787217"
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
  
## <a name="requirements"></a>Anforderungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
