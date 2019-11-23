---
title: EmitManifest-Methode
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: f3bb978b8358992fd9aa7da922e28efc1ed1a951
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446482"
---
# <a name="emitmanifest-method"></a>EmitManifest-Methode
Emits the final manifest. Call this method after importing all other files and setting all options. Do not call this method for unbound modules.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 ID of the assembly.  
  
 `pdwReserveSize`  
 Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).  
  
 `ptkManifest`  
 Optionally receives the assembly manifest token.  
  
## <a name="return-value"></a>Rückgabewert  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>Anforderungen  
 Requires alink.h.  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
