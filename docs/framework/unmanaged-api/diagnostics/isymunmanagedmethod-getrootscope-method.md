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
ms.openlocfilehash: 071738c8fb9b40457215e21172240aa7e77198cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699468"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="21100-102">ISymUnmanagedMethod::GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="21100-102">ISymUnmanagedMethod::GetRootScope Method</span></span>

<span data-ttu-id="21100-103">Ruft den lexikalischen Stamm Gültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="21100-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="21100-104">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="21100-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21100-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="21100-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21100-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="21100-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="21100-107">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedScope](isymunmanagedscope-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="21100-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21100-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="21100-108">Return Value</span></span>  

 <span data-ttu-id="21100-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="21100-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21100-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21100-110">Requirements</span></span>  

 <span data-ttu-id="21100-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="21100-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21100-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21100-112">See also</span></span>

- [<span data-ttu-id="21100-113">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21100-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
