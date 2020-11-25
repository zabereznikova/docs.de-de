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
ms.openlocfilehash: 69b72ce66a203f403fcfe0fd4b4e728ece7397e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725871"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="35006-102">ISymUnmanagedScope::GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="35006-102">ISymUnmanagedScope::GetStartOffset Method</span></span>

<span data-ttu-id="35006-103">Ruft den Start Offset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="35006-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35006-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35006-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35006-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35006-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="35006-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der den Start Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="35006-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35006-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35006-107">Return Value</span></span>  

 <span data-ttu-id="35006-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="35006-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35006-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="35006-109">Requirements</span></span>  

 <span data-ttu-id="35006-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="35006-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35006-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35006-111">See also</span></span>

- [<span data-ttu-id="35006-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35006-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="35006-113">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="35006-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
