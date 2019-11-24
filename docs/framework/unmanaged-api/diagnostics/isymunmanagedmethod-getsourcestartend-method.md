---
title: ISymUnmanagedMethod::GetSourceStartEnd-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: 01ab69b73a7bc4929e2ebd49b3847f8d7c4646a2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448862"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="c2174-102">ISymUnmanagedMethod::GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="c2174-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="c2174-103">Gets the start and end document positions for the source of this method.</span><span class="sxs-lookup"><span data-stu-id="c2174-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="c2174-104">The first array position is the start, and the second array position is the end.</span><span class="sxs-lookup"><span data-stu-id="c2174-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2174-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2174-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2174-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2174-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="c2174-107">[in] The starting and ending source documents.</span><span class="sxs-lookup"><span data-stu-id="c2174-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="c2174-108">[in] The starting and ending lines in the corresponding source documents.</span><span class="sxs-lookup"><span data-stu-id="c2174-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="c2174-109">[in] The starting and ending columns in the corresponding source documents.</span><span class="sxs-lookup"><span data-stu-id="c2174-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c2174-110">[out] `true` if positions were defined; otherwise, `false`.</span><span class="sxs-lookup"><span data-stu-id="c2174-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2174-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c2174-111">Return Value</span></span>  
 <span data-ttu-id="c2174-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="c2174-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2174-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2174-113">Requirements</span></span>  
 <span data-ttu-id="c2174-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2174-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2174-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2174-115">See also</span></span>

- [<span data-ttu-id="c2174-116">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2174-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
