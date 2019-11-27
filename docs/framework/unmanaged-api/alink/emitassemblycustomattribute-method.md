---
title: EmitAssemblyCustomAttribute-Methode
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
ms.openlocfilehash: ec0a86e3396ad42152bc0a244f74ad13deba16e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446510"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute-Methode
Aufgerufen, um benutzerdefinierte Attribute auf Assemblyebene festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly.  
  
 `FileToken`  
 Die Datei, die das Attribut deaktiviert. Kann NULL sein, wenn `AssemblyID` keinen ungebundenen NetModule angibt.  
  
 `tkType`  
 Der Typ des benutzerdefinierten Attributs.  
  
 `pCustomValue`  
 Benutzerdefinierte Wertdaten.  
  
 `cbCustomValue`  
 Länge von benutzerdefinierten Wertdaten.  
  
 `bSecurity`  
 TRUE, wenn das benutzerdefinierte Attribut mit der Assemblysignatur verknüpft ist.  
  
 `bAllowMulti`  
 TRUE, wenn mehrere Attribute ausgegeben werden sollen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
