---
title: ISymUnmanagedScope::GetEndOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 14e747e81e467019d464212e75513bdf98344916
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678362"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="2cc7b-102">ISymUnmanagedScope::GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="2cc7b-102">ISymUnmanagedScope::GetEndOffset Method</span></span>

<span data-ttu-id="2cc7b-103">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="2cc7b-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cc7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cc7b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cc7b-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="2cc7b-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der den Endoffset empfängt.</span><span class="sxs-lookup"><span data-stu-id="2cc7b-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cc7b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2cc7b-107">Return Value</span></span>  

 <span data-ttu-id="2cc7b-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2cc7b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cc7b-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2cc7b-109">Requirements</span></span>  

 <span data-ttu-id="2cc7b-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2cc7b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc7b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cc7b-111">See also</span></span>

- [<span data-ttu-id="2cc7b-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cc7b-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="2cc7b-113">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="2cc7b-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
