---
title: ISymUnmanagedReader::GetUserEntryPoint-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: 50f41bb55b7c3dc45646a465032074ce90be0abf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444506"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a>ISymUnmanagedReader::GetUserEntryPoint-Methode
Returns the method that was specified as the user entry point for the module, if any. For example, this method could be the user's main method rather than compiler-generated stubs before the main method.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a>Parameter  
 `pToken`  
 [out] A pointer to a variable that receives the entry point.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK if the method succeeds; otherwise, E_FAIL or some other error code.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
