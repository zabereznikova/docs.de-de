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
ms.openlocfilehash: 7e26c272ee1ecf03f7d2a347cf7ca2cc3efa2122
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699559"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="26a2f-102">ISymUnmanagedMethod::GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="26a2f-102">ISymUnmanagedMethod::GetNamespace Method</span></span>

<span data-ttu-id="26a2f-103">Ruft den Namespace ab, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="26a2f-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a2f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26a2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26a2f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="26a2f-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="26a2f-106">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="26a2f-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26a2f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="26a2f-107">Return Value</span></span>  

 <span data-ttu-id="26a2f-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="26a2f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a2f-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="26a2f-109">Requirements</span></span>  

 <span data-ttu-id="26a2f-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="26a2f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a2f-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26a2f-111">See also</span></span>

- [<span data-ttu-id="26a2f-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26a2f-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
