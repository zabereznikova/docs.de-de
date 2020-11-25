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
ms.openlocfilehash: 131f5d951e524ef48f2cfe1e3e88ef80ac21c452
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703680"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [ALink-API](index.md)
