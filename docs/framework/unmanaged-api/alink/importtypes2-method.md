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
ms.openlocfilehash: 8dae903ab76ab83ac0818c4bc4a76e81094bdf65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445663"
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
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
