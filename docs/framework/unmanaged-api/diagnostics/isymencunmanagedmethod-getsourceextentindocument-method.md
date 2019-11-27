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
ms.openlocfilehash: b8e72745eff09c6707afe5a5f20a1ddf38b239ae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448614"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="4c9c8-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="4c9c8-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="4c9c8-103">Ruft die kleinste anfangs Linie und die größte Endzeile für die Methode in einem bestimmten Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="4c9c8-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c9c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c9c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c9c8-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="4c9c8-106">in Ein Zeiger auf das Dokument.</span><span class="sxs-lookup"><span data-stu-id="4c9c8-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="4c9c8-107">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Start Zeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="4c9c8-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="4c9c8-108">vorgenommen Ein Zeiger auf eine `ULONG32`, die die Endzeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="4c9c8-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c9c8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4c9c8-109">Return Value</span></span>  
 <span data-ttu-id="4c9c8-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4c9c8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c9c8-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4c9c8-111">Requirements</span></span>  
 <span data-ttu-id="4c9c8-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="4c9c8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9c8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c9c8-113">See also</span></span>

- [<span data-ttu-id="4c9c8-114">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c9c8-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
