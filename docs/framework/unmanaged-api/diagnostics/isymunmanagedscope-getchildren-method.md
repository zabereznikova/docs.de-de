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
ms.openlocfilehash: c6d21f40c260890c9c88dcdfccd7e31161024ba3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614863"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="070f8-102">ISymUnmanagedScope::GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="070f8-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="070f8-103">Ruft die untergeordneten Elemente dieses Gültigkeits Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="070f8-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="070f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="070f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="070f8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="070f8-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="070f8-106">in Ein-Wert `ULONG32` , der die Größe des `children` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="070f8-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="070f8-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der untergeordneten Elemente erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="070f8-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="070f8-108">vorgenommen Das zurückgegebene Array von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="070f8-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="070f8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="070f8-109">Return Value</span></span>  
 <span data-ttu-id="070f8-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="070f8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="070f8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="070f8-111">Requirements</span></span>  
 <span data-ttu-id="070f8-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="070f8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="070f8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="070f8-113">See also</span></span>

- [<span data-ttu-id="070f8-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="070f8-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="070f8-115">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="070f8-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
