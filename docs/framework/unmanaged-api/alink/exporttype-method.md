---
title: ExportType-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
ms.openlocfilehash: b8db08b22765bac0ed2fe058db49d6882b8d22df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684797"
---
# <a name="exporttype-method"></a>ExportType-Methode

Gibt an, dass ein Typ exportierbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `AssemblyID`  
 Die ID der Assembly, aus der exportiert werden soll.  
  
 `FileToken`  
 Dateitoken oder Assembly-ID der Datei, die den exportierbaren Typ definiert.  
  
 `TypeToken`  
 Das Token vom Typ, das als exportierbar erstellt werden soll.  
  
 `pszTypename`  
 Der voll qualifizierte Typname, der als exportierbar erstellt werden soll.  
  
 `dwFlags`  
 `ComType` Flags wie `tdPublic` oder `tdNested` . Dieser Parameter kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übergeben werden.  
  
 `pType`  
 Empfängt das Token für den exportierten Typ.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
