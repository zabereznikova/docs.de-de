---
title: GetFileDef-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
ms.openlocfilehash: 6a561205602920123176bd421ca2ef1b601166c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426050"
---
# <a name="getfiledef-method"></a>GetFileDef-Methode
Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 ID of the assembly.  
  
 `TargetFile`  
 Token of the added file as retrieved from AddFile Method or AddImport Method.  
  
 `pScope`  
 Receives the FileDef token.  
  
## <a name="return-value"></a>Rückgabewert  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>Anforderungen  
 Requires alink.h  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
