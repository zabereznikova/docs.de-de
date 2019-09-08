---
title: ExportTypeForwarder-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ae4ddd07a2a3d3ab9b5d024eceb43329db96915
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787505"
---
# <a name="exporttypeforwarder-method"></a>ExportTypeForwarder-Methode
Fügt der Typtabelle der angegebenen Assembly eine Typweiterleitung hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `tkAssemblyRef`  
 Verweis auf die Assembly, auf die die Typweiterleitung verweist.  
  
 `pszTypename`  
 Der voll qualifizierte Typname, der exportiert werden soll.  
  
 `dwFlags`  
 `ComType`Flags wie `tdPublic` oder `tdNested`. Dieser Wert kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.  
  
 `pType`  
 Empfängt das Token des exportierten Typs. Dies ist nur für das Ausgeben von Untertypen erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
