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
ms.openlocfilehash: fded6b95144d4088a2abc8dfcc4ef8eda331c34f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438421"
---
# <a name="exportnestedtype-method"></a>ExportNestedType-Methode
Gibt die zu exportierenden Typen als exportierbar an. Die [ExportType-Methode](exporttype-method.md) kann auch die in die Liste eingefügten Typen exportieren, diese Methode ist jedoch schneller.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 Die ID der zu exportierenden Assembly.  
  
 `FileToken`  
 Dateitoken oder Assemblydatei, die den Typ definiert, der exportierbar gemacht werden soll.  
  
 `TypeToken`  
 Typtoken vom Typ, das als exportierbar erstellt werden soll.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Der voll qualifizierte Typname, der exportiert werden soll.  
  
 `dwFlags`  
 `ComType` Flags, z. b. `tdPublic` oder `tdNested`. Dieser Wert kann an die [DefineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übermittelt werden.  
  
 `pType`  
 Empfängt das Token für den exportierten Typ.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
