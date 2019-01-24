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
ms.openlocfilehash: a2bba44af50607772f2a52203a47e21d8699f78b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716151"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="c6c4b-102">ISymUnmanagedMethod::GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="c6c4b-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="c6c4b-103">Ruft den Namespace, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c6c4b-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6c4b-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6c4b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6c4b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c6c4b-106">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c6c4b-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6c4b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c6c4b-107">Return Value</span></span>  
 <span data-ttu-id="c6c4b-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c6c4b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c4b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6c4b-109">Requirements</span></span>  
 <span data-ttu-id="c6c4b-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6c4b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c4b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6c4b-111">See also</span></span>
- [<span data-ttu-id="c6c4b-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6c4b-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
