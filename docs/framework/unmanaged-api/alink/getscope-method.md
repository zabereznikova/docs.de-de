---
title: GetScope-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: fd5ae6ef40cb171c33132df0f640acbef96d69b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684672"
---
# <a name="getscope-method"></a>GetScope-Methode

Ruft einen Import Bereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `AssemblyID`  
 Eindeutige ID der Assembly, in die importiert werden soll.  
  
 `FileToken`  
 Eindeutige ID der Datei, aus der importiert werden soll.  
  
 `dwScope`  
 NULL basierter Gültigkeitsbereich, der importiert werden soll.  
  
 `ppImportScope`  
 Empfängt die [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) -Schnittstelle für den Bereich.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
