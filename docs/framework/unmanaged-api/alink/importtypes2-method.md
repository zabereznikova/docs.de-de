---
title: ImportTypes2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce09eca30e1edb9e1afc02216a07955a5fed4fd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787256"
---
# <a name="importtypes2-method"></a>ImportTypes2-Methode
Initiiert den Import von-Typen. Mit dieser Methode können Sie beginnen, Typen aus jedem Bereich zu importieren, der über die [ImportFile-Methode](importfile-method.md)importiert wird  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly, in die importiert werden soll.  
  
 `FileToken`  
 Die ID der Datei, aus der importiert werden soll.  
  
 `dwScope`  
 NULL basierter Bereich, aus dem importiert werden soll.  
  
 `phEnum`  
 Empfängt das Enumeratorhandle für die Typen im angegebenen Bereich.  
  
 `ppImportScope`  
 Empfängt optional die [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) -Schnittstelle.  
  
 `pdwCountOfTypes`  
 Empfängt optional die Anzahl der Typen im angegebenen Bereich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
