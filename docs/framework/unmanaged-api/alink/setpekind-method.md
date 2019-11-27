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
ms.openlocfilehash: dfbc10bdbe633450dee2e27524c29ead21fb739e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445537"
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
 Das Token der Datei, für die der PE-Typ festgelegt werden soll. Kann NULL sein, wenn `AssemblyID` keinen ungebundenen NetModule angibt.  
  
 `dwPEKind`  
 Der Typ des PE, wie von der [corpeer Kind-Enumeration](../metadata/corpekind-enumeration.md)angegeben.  
  
 `dwMachine`  
 Die Architektur des Ziel Computers, wie im NT-Header angegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert Alink. h.  
  
## <a name="see-also"></a>Siehe auch

- [GetPEKind-Methode](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
