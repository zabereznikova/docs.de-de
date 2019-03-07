---
title: ExportNestedType-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49dc456df684d6905370ee6ab8c8883449bea990
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498041"
---
# <a name="exportnestedtype-method"></a>ExportNestedType-Methode
Gibt geschachtelte Typen als "Exportierbar" markieren. Die [ExportType-Methode](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExportNestedType(  
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
 ID der Assembly zum Exportieren aus.  
  
 `FileToken`  
 Datei-Token oder übergeordnete Assembly der Datei, definiert den Typ als exportierbar festgelegt werden.  
  
 `TypeToken`  
 Geben Sie ein Token des Typs als exportierbar festgelegt werden.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Vollqualifizierten Typnamen zu exportieren.  
  
 `dwFlags`  
 `ComType` Flags, z. B. `tdPublic` oder `tdNested`. Dieser Wert kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Empfängt die Token für den exportierten Typ.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch
- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
