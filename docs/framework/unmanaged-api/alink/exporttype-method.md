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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95ff27143453e7772b4a463fa66ca039bbb715fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789934"
---
# <a name="exporttype-method"></a>ExportType-Methode
Gibt an, dass ein Typ exportiert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 Die ID der Assembly zum Exportieren aus.  
  
 `FileToken`  
 Datei-Token "oder" Assembly-ID der Datei, die den exportierbaren Typ definiert.  
  
 `TypeToken`  
 Token des Typs als exportierbar festgelegt werden.  
  
 `pszTypename`  
 Voll gekennzeichneten Typnamen als exportierbar festgelegt werden.  
  
 `dwFlags`  
 `ComType` Flags, z. B. `tdPublic` oder `tdNested`. Dieser Parameter kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
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
