---
title: ISymUnmanagedScope::GetChildren-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9c05efefb985e4b9ec9349974f243c4828d9bcf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478816"
---
# <a name="isymunmanagedscopegetchildren-method"></a>ISymUnmanagedScope::GetChildren-Methode
Ruft die untergeordneten Elemente dieses Bereichs ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cChildren`  
 [in] Ein `ULONG32` , der angibt, dass der Größe des der `children` Array.  
  
 `pcChildren`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die untergeordneten Elemente enthalten.  
  
 `children`  
 [out] Das zurückgegebene Array der untergeordneten Elemente.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedScope-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [GetParent-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
