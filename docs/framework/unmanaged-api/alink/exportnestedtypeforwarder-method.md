---
title: ExportNestedTypeForwarder-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dfb31a2fad8a07b3821ac85bbb43b25693f11d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder-Methode
Die Tabelle der angegebenen Assembly hinzugefügt typweiterleitung für einen geschachtelten Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly exportieren.  
  
 `FileToken`  
 Datei-Token oder Assembly-ID der Datei, die den Typ definiert.  
  
 `TypeToken`  
 Token für den Typ.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Voll qualifizierten Typnamen zu exportieren.  
  
 `dwFlags`  
 `ComType` Flags, z. B. `tdPublic` oder `tdNested`.  
  
 `pType`  
 Empfängt Token Exporttyp an. Dies ist nur für das Ausgeben von geschachtelten Typen erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
