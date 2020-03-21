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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179412"
---
# <a name="exportnestedtype-method"></a>ExportNestedType-Methode
Gibt geschachtelte Typen als exportierbar an. Die [ExportType-Methode](exporttype-method.md) kann auch geschachtelte Typen exportieren, aber diese Methode ist schneller.  
  
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
 ID der Assembly, aus der exportiert werden soll.  
  
 `FileToken`  
 Dateitoken oder Assembly der Datei, die den Typ definiert, der exportiert werden soll.  
  
 `TypeToken`  
 Typtoken des Typs, der exportiert werden soll.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Vollständig qualifizierter Typname zum Exportieren.  
  
 `dwFlags`  
 `ComType`Flags wie `tdPublic` `tdNested`oder . Dieser Wert kann an [defineExportedType-Methode](../metadata/imetadataassemblyemit-defineexportedtype-method.md)übergeben werden.  
  
 `pType`  
 Empfängt Token für exportierten Typ.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 Erfordert alink.h  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
