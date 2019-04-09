---
title: ISymUnmanagedMethod::GetScopeFromOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0e859ba8b6ec247073b0b69b035ea4cf074ab05
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149291"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="12fa5-102">ISymUnmanagedMethod::GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="12fa5-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="12fa5-103">Ruft den umfassendsten lexikalischen Gültigkeitsbereich innerhalb dieser Methode, die den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="12fa5-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="12fa5-104">Dies kann verwendet werden, um die lokalen Variablen starten.</span><span class="sxs-lookup"><span data-stu-id="12fa5-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12fa5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="12fa5-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12fa5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="12fa5-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="12fa5-107">[in] Ein `ULONG` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="12fa5-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="12fa5-108">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="12fa5-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12fa5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="12fa5-109">Return Value</span></span>  
 <span data-ttu-id="12fa5-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="12fa5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12fa5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12fa5-111">Requirements</span></span>  
 <span data-ttu-id="12fa5-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12fa5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fa5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12fa5-113">See also</span></span>

- [<span data-ttu-id="12fa5-114">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12fa5-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
