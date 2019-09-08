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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77d54f6c8f67dda5132518d1fbd579a91ce82071
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777441"
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
 Die Datei, die das Attribut deaktiviert. Kann NULL sein, `AssemblyID` wenn kein ungebundenes NetModule angibt.  
  
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
  
## <a name="requirements"></a>Anforderungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
