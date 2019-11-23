---
title: ISymUnmanagedScope::GetNamespaces-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: b765294826a5da4010cdd2db79b50667a6f1cdb4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446305"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="7575e-102">ISymUnmanagedScope::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="7575e-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="7575e-103">Gets the namespaces that are being used within this scope.</span><span class="sxs-lookup"><span data-stu-id="7575e-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7575e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7575e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7575e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7575e-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="7575e-106">[in] Die Größe des `namespaces`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="7575e-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="7575e-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span><span class="sxs-lookup"><span data-stu-id="7575e-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="7575e-108">[out] The array that receives the namespaces.</span><span class="sxs-lookup"><span data-stu-id="7575e-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7575e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7575e-109">Return Value</span></span>  
 <span data-ttu-id="7575e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="7575e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7575e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7575e-111">Requirements</span></span>  
 <span data-ttu-id="7575e-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7575e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7575e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7575e-113">See also</span></span>

- [<span data-ttu-id="7575e-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7575e-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
