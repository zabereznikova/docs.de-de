---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 442584cffe4b4ae44702892587e261d41abf4e8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150422"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="3c6ac-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="3c6ac-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="3c6ac-103">Ruft Starten des kleinsten und größten End Zeile für die Methode in einem bestimmten Dokument.</span><span class="sxs-lookup"><span data-stu-id="3c6ac-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c6ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c6ac-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c6ac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c6ac-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="3c6ac-106">[in] Ein Zeiger auf das Dokument.</span><span class="sxs-lookup"><span data-stu-id="3c6ac-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="3c6ac-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Startzeile.</span><span class="sxs-lookup"><span data-stu-id="3c6ac-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="3c6ac-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die letzte Zeile.</span><span class="sxs-lookup"><span data-stu-id="3c6ac-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c6ac-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3c6ac-109">Return Value</span></span>  
 <span data-ttu-id="3c6ac-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3c6ac-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c6ac-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c6ac-111">Requirements</span></span>  
 <span data-ttu-id="3c6ac-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3c6ac-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c6ac-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c6ac-113">See also</span></span>

- [<span data-ttu-id="3c6ac-114">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c6ac-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
