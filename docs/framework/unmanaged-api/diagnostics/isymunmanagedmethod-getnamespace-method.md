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
ms.openlocfilehash: b8bbedb4c60a2df6070373f2b6a104fff094869a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448964"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="a1e56-102">ISymUnmanagedMethod::GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="a1e56-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="a1e56-103">Ruft den Namespace ab, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a1e56-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1e56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1e56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1e56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1e56-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a1e56-106">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a1e56-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1e56-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a1e56-107">Return Value</span></span>  
 <span data-ttu-id="a1e56-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a1e56-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1e56-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a1e56-109">Requirements</span></span>  
 <span data-ttu-id="a1e56-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a1e56-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e56-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1e56-111">See also</span></span>

- [<span data-ttu-id="a1e56-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1e56-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
