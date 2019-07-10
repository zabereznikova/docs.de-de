---
title: ISymUnmanagedMethod::GetRootScope-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8956d72d25f240eff653d3eefb92b68431f4e2ae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771782"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="48511-102">ISymUnmanagedMethod::GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="48511-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="48511-103">Ruft den lexikalischen Stammgültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="48511-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="48511-104">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="48511-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48511-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="48511-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48511-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="48511-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="48511-107">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="48511-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48511-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48511-108">Return Value</span></span>  
 <span data-ttu-id="48511-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="48511-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48511-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48511-110">Requirements</span></span>  
 <span data-ttu-id="48511-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="48511-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48511-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48511-112">See also</span></span>

- [<span data-ttu-id="48511-113">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48511-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
