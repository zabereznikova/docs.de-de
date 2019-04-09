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
ms.openlocfilehash: 67073f04cfe981dd383369029d9a4b436929a0a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117844"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute-Methode
Der Aufruf zum Festlegen der benutzerdefinierten Attribute auf Assemblyebene.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 Datei, die das Attribut definiert. Kann NULL sein, wenn `AssemblyID` gibt nicht an eine nicht gebundene NETMODULE-Datei.  
  
 `tkType`  
 Der Typ des benutzerdefinierten Attributs.  
  
 `pCustomValue`  
 Benutzerdefinierte-Wert-Daten.  
  
 `cbCustomValue`  
 Länge der Daten mit benutzerdefinierten Werten.  
  
 `bSecurity`  
 TRUE, wenn das benutzerdefinierte Attribut zum Signieren der Assembly verknüpft ist.  
  
 `bAllowMulti`  
 True, wenn mehrere Attribute, die ausgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
