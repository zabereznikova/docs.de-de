---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: cba4af737cc6a6441d38ba0f940fffe54f5c4f09
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449063"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="e05f7-102">ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="e05f7-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="e05f7-103">Gets the number of local variables.</span><span class="sxs-lookup"><span data-stu-id="e05f7-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e05f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e05f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e05f7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e05f7-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="e05f7-106">[in] The metadata token of methods.</span><span class="sxs-lookup"><span data-stu-id="e05f7-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="e05f7-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span><span class="sxs-lookup"><span data-stu-id="e05f7-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e05f7-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e05f7-108">Return Value</span></span>  
 <span data-ttu-id="e05f7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="e05f7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e05f7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e05f7-110">Requirements</span></span>  
 <span data-ttu-id="e05f7-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e05f7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05f7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e05f7-112">See also</span></span>

- [<span data-ttu-id="e05f7-113">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e05f7-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
