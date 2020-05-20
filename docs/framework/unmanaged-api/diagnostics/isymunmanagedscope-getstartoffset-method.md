---
title: ISymUnmanagedScope::GetStartOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 071ad6c24804eecb0f2260d54c854f22ff997bc1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611015"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="ad09c-102">ISymUnmanagedScope::GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ad09c-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="ad09c-103">Ruft den Start Offset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="ad09c-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad09c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad09c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad09c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad09c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ad09c-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der den Start Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="ad09c-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad09c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ad09c-107">Return Value</span></span>  
 <span data-ttu-id="ad09c-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ad09c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad09c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad09c-109">Requirements</span></span>  
 <span data-ttu-id="ad09c-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="ad09c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad09c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad09c-111">See also</span></span>

- [<span data-ttu-id="ad09c-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad09c-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="ad09c-113">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ad09c-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
