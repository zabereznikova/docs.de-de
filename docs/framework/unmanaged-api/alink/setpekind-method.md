---
title: SetPEKind-Methode
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179387"
---
# <a name="setpekind-method"></a>SetPEKind-Methode
Bestimmt den portablen ausführbaren Typ, entweder maschinenspezifisch oder maschinenunabhängig.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 ID der Assembly.  
  
 `FileToken`  
 Token der Datei, für die der PE-Typ festgelegt werden soll. Kann NULL `AssemblyID` sein, wenn es nicht auf ein ungebundenes Netmodule hinweist.  
  
 `dwPEKind`  
 Der Pe-Typ, wie durch die [CorPEKind-Enumeration](../metadata/corpekind-enumeration.md)angegeben.  
  
 `dwMachine`  
 Die Zielcomputerarchitektur, wie im NT-Header angegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Weitere Informationen

- [GetPEKind-Methode](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
