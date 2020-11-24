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
ms.openlocfilehash: 45adda6551e1cec994f59acbb0e8d2b5c56c4df6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684810"
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
 `ComType` Flags wie `tdPublic` oder `tdNested` .  
  
 `pType`  
 Empfängt das Token des Export Typs. Dies ist nur für das Ausgeben von Untertypen erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
