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
ms.openlocfilehash: eb8112d6d2b5c2cbb257db2f20ff4be5a84e827b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787475"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder-Methode
Fügt der Typtabelle der angegebenen Assembly eine Typweiterleitung für einen geblierten Typ hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 Die ID der Assembly, aus der exportiert werden soll.  
  
 `FileToken`  
 Dateitoken oder Assembly-ID der Datei, die den Typ definiert.  
  
 `TypeToken`  
 Token für den Typ.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Der voll qualifizierte Typname, der exportiert werden soll.  
  
 `dwFlags`  
 `ComType`Flags wie `tdPublic` oder `tdNested`.  
  
 `pType`  
 Empfängt das Token des Export Typs. Dies ist nur für das Ausgeben von Untertypen erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
