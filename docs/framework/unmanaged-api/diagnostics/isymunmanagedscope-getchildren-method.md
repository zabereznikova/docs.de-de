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
ms.openlocfilehash: c7e9d2fe94c33127d8b105333ad6dac9d6cc5af6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446372"
---
# <a name="isymunmanagedscopegetchildren-method"></a>ISymUnmanagedScope::GetChildren-Methode
Ruft die untergeordneten Elemente dieses Gültigkeits Bereichs ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cChildren`  
 in Ein-`ULONG32`, der die Größe des `children` Arrays angibt.  
  
 `pcChildren`  
 vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers empfängt, der zum enthalten der untergeordneten Elemente erforderlich ist.  
  
 `children`  
 vorgenommen Das zurückgegebene Array von untergeordneten Elementen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedScope-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [GetParent-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
