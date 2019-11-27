---
title: ImportTypes-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 76d2b163f959111923bffb1348890f6fbb29828e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445675"
---
# <a name="importtypes-method"></a>ImportTypes-Methode
Initiiert den Import von Typen aus jedem Bereich, der über die [ImportFile-Methode](importfile-method.md)importiert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly, in die importiert werden soll.  
  
 `FileToken`  
 Die ID der Datei, aus der importiert werden soll.  
  
 `dwScope`  
 NULL basierter Gültigkeitsbereich, der importiert werden soll.  
  
 `phEnum`  
 Empfängt das Enumeratorhandle für die Typen in diesem Bereich.  
  
 `ppImportScope`  
 Empfängt optional die [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) -Schnittstelle.  
  
 `pdwCountOfTypes`  
 Empfängt optional die Anzahl der Typen im aufgeführten Bereich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
