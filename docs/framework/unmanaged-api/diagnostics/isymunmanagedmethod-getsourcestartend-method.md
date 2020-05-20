---
title: ISymUnmanagedMethod::GetSourceStartEnd-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: 25e797fdf563a01ab727f16e7173eec2552eeb27
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614421"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="1066b-102">ISymUnmanagedMethod::GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="1066b-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="1066b-103">Ruft die Start-und Enddokument Positionen für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="1066b-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="1066b-104">Die erste Array Position ist der Start, und die zweite Array Position ist das Ende.</span><span class="sxs-lookup"><span data-stu-id="1066b-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1066b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1066b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1066b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1066b-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="1066b-107">in Die Start-und endquell Dokumente.</span><span class="sxs-lookup"><span data-stu-id="1066b-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="1066b-108">in Die Anfangs-und Endzeilen in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="1066b-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="1066b-109">in Die Anfangs-und Endspalten in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="1066b-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1066b-110">[out] `true` , wenn Positionen definiert wurden. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="1066b-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1066b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1066b-111">Return Value</span></span>  
 <span data-ttu-id="1066b-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1066b-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1066b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1066b-113">Requirements</span></span>  
 <span data-ttu-id="1066b-114">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1066b-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1066b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1066b-115">See also</span></span>

- [<span data-ttu-id="1066b-116">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1066b-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
