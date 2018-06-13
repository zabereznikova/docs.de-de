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
ms.openlocfilehash: 417ce67d807fddd3b99ceff4b05f1524db3044e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430527"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="5d539-102">ISymUnmanagedMethod::GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="5d539-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="5d539-103">Ruft den lexikalischen Stammgültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="5d539-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="5d539-104">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="5d539-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d539-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d539-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d539-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d539-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5d539-107">[out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5d539-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d539-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d539-108">Return Value</span></span>  
 <span data-ttu-id="5d539-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5d539-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d539-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d539-110">Requirements</span></span>  
 <span data-ttu-id="5d539-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5d539-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d539-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d539-112">See Also</span></span>  
 [<span data-ttu-id="5d539-113">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d539-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
