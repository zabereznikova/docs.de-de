---
title: ISymUnmanagedScope2::GetConstantCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a063d25e180be466421c14ca65a5b4cea881fc8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127324"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="3a76d-102">ISymUnmanagedScope2::GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="3a76d-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="3a76d-103">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="3a76d-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a76d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a76d-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a76d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a76d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3a76d-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Konstanten enthalten.</span><span class="sxs-lookup"><span data-stu-id="3a76d-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a76d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3a76d-107">Return Value</span></span>  
 <span data-ttu-id="3a76d-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3a76d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a76d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a76d-109">Requirements</span></span>  
 <span data-ttu-id="3a76d-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3a76d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a76d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a76d-111">See also</span></span>

- [<span data-ttu-id="3a76d-112">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a76d-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
