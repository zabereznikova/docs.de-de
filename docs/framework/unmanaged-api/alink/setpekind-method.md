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
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680039"
---
# <a name="setpekind-method"></a>SetPEKind-Methode

Bestimmt den Typ der portablen ausführbaren Datei, entweder Computer spezifisch oder Computer agnostisch.  
  
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
 Die ID der Assembly.  
  
 `FileToken`  
 Das Token der Datei, für die der PE-Typ festgelegt werden soll. Kann NULL sein, wenn `AssemblyID` kein ungebundenes NetModule angibt.  
  
 `dwPEKind`  
 Der Typ des PE, wie von der [corpeer Kind-Enumeration](../metadata/corpekind-enumeration.md)angegeben.  
  
 `dwMachine`  
 Die Architektur des Ziel Computers, wie im NT-Header angegeben.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [GetPEKind-Methode](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [ALink-API](index.md)
