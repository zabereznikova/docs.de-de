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
ms.openlocfilehash: cda30f3c73bf75c37ff79fc415e02382b053807e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614486"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="b8695-102">ISymUnmanagedMethod::GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="b8695-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="b8695-103">Ruft den Namespace ab, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b8695-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8695-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8695-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8695-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8695-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b8695-106">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b8695-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8695-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8695-107">Return Value</span></span>  
 <span data-ttu-id="b8695-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b8695-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8695-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8695-109">Requirements</span></span>  
 <span data-ttu-id="b8695-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="b8695-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8695-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8695-111">See also</span></span>

- [<span data-ttu-id="b8695-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8695-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
