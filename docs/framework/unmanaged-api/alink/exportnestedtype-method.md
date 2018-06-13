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
ms.openlocfilehash: 0afe4daa1c85f3e15addac55bdbe631d40e03f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407564"
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
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 ID der Assembly exportieren.  
  
 `FileToken`  
 Datei-Token oder übergeordnete Assembly der Datei, definiert den Typ als exportierbar festgelegt werden.  
  
 `TypeToken`  
 Geben Sie ein Token vom Typ als exportierbar festgelegt werden.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Voll qualifizierten Typnamen zu exportieren.  
  
 `dwFlags`  
 `ComType` Flags, z. B. `tdPublic` oder `tdNested`. Dieser Wert möglicherweise übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Empfängt Token für den exportierten Typ.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
