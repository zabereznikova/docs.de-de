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
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="d07ef-102">ISymUnmanagedScope::GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="d07ef-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="d07ef-103">Ruft die untergeordneten Elemente dieses Gültigkeits Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="d07ef-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d07ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d07ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d07ef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d07ef-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="d07ef-106">in Ein-`ULONG32`, der die Größe des `children` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="d07ef-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="d07ef-107">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers empfängt, der zum enthalten der untergeordneten Elemente erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d07ef-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="d07ef-108">vorgenommen Das zurückgegebene Array von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="d07ef-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d07ef-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d07ef-109">Return Value</span></span>  
 <span data-ttu-id="d07ef-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d07ef-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d07ef-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d07ef-111">Requirements</span></span>  
 <span data-ttu-id="d07ef-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d07ef-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07ef-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d07ef-113">See also</span></span>

- [<span data-ttu-id="d07ef-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d07ef-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="d07ef-115">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="d07ef-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
