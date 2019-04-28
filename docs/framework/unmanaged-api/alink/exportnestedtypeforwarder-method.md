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
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789908"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder-Methode
Fügt eine typweiterleitung für einen geschachtelten Typ der Typtabelle der angegebenen Assembly hinzu.  
  
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
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly zum Exportieren aus.  
  
 `FileToken`  
 Datei-Token "oder" Assembly-ID der Datei, die den Typ definiert.  
  
 `TypeToken`  
 Token für den Typ.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Vollqualifizierten Typnamen zu exportieren.  
  
 `dwFlags`  
 `ComType` Flags, z. B. `tdPublic` oder `tdNested`.  
  
 `pType`  
 Empfängt die Token des Exporttyps. Dies ist nur für die Ausgabe von geschachtelter Typen erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
