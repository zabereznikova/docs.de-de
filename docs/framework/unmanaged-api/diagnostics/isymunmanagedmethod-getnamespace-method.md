---
title: ISymUnmanagedMethod::GetNamespace-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53a47cf67edb36b06c92be83cb23c2e1dd1e75cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424429"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="6e545-102">ISymUnmanagedMethod::GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="6e545-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="6e545-103">Ruft den Namespace, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6e545-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e545-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e545-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e545-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e545-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6e545-106">[out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6e545-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e545-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e545-107">Return Value</span></span>  
 <span data-ttu-id="6e545-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6e545-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e545-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e545-109">Requirements</span></span>  
 <span data-ttu-id="6e545-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6e545-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e545-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e545-111">See Also</span></span>  
 [<span data-ttu-id="6e545-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e545-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
