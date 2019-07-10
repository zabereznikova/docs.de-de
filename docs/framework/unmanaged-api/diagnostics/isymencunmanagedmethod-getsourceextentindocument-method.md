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
ms.openlocfilehash: e4948a853434b14845983addb0e6fa4012279084
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776870"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="d3fa7-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="d3fa7-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="d3fa7-103">Ruft Starten des kleinsten und größten End Zeile für die Methode in einem bestimmten Dokument.</span><span class="sxs-lookup"><span data-stu-id="d3fa7-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3fa7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3fa7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3fa7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3fa7-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="d3fa7-106">[in] Ein Zeiger auf das Dokument.</span><span class="sxs-lookup"><span data-stu-id="d3fa7-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="d3fa7-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Startzeile.</span><span class="sxs-lookup"><span data-stu-id="d3fa7-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="d3fa7-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die letzte Zeile.</span><span class="sxs-lookup"><span data-stu-id="d3fa7-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3fa7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d3fa7-109">Return Value</span></span>  
 <span data-ttu-id="d3fa7-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d3fa7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3fa7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3fa7-111">Requirements</span></span>  
 <span data-ttu-id="d3fa7-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d3fa7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3fa7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3fa7-113">See also</span></span>

- [<span data-ttu-id="d3fa7-114">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3fa7-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
