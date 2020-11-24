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
ms.openlocfilehash: 4e6ceabf37056bfc25247266be2c7801cb0e13e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684771"
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
 `ComType` Flags wie `tdPublic` oder `tdNested` . Dieser Wert kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.  
  
 `pType`  
 Empfängt das Token des exportierten Typs. Dies ist nur für das Ausgeben von Untertypen erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
