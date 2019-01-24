---
title: ImportFileEx-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0381ee61a0128a8ae303d44198f8d391b4531a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660618"
---
# <a name="importfileex-method"></a>ImportFileEx-Methode
Importiert die angegebene Assembly oder ein ungebundenes Modul angegebene.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszFilename`  
 Voll gekennzeichnete Name der Datei, aus denen importiert.  
  
 `pszTargetName`  
 Optionaler Name der Zieldatei.  
  
 `fSmartImport`  
 True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.  
  
 `dwOpenFlags`  
 Flags, die zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Empfängt die ID der Datei importiert wird.  
  
 `ppAssemblyScope`  
 Import Assemblybereich empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle. Wird auf NULL festgelegt werden, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Empfängt die Anzahl der importierten Dateien bzw. Bereiche.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h an.  
  
## <a name="see-also"></a>Siehe auch
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
