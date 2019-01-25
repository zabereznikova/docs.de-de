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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6591fb4a2b4944dc0d02f70f0f90ffd87e071c47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735000"
---
# <a name="importtypes-method"></a>ImportTypes-Methode
Initiiert das Importieren von Typen aus jedem Bereich über importiert [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly zu importieren.  
  
 `FileToken`  
 Die ID der Datei zum Importieren aus.  
  
 `dwScope`  
 Nullbasierte Bereich importiert.  
  
 `phEnum`  
 Enumeratorhandle für die Typen empfängt in diesem Bereich.  
  
 `ppImportScope`  
 Empfängt optional [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle.  
  
 `pdwCountOfTypes`  
 Empfängt optional die Anzahl der Typen im angegebenen Bereich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch
- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
