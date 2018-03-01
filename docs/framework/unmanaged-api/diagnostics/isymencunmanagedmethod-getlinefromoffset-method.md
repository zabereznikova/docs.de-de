---
title: ISymENCUnmanagedMethod::GetLineFromOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 535c0310a3220c5691f26c9081f6d2f747196e91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="acee1-102">ISymENCUnmanagedMethod::GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="acee1-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="acee1-103">Ruft die Zeileninformationen ein Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="acee1-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="acee1-104">Wenn der Offset-Parameter (`dwOffset`) ein Sequenzpunkt ist diese Methode ruft die Zeileninformationen vorherigen Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="acee1-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acee1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="acee1-105">Syntax</span></span>  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acee1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="acee1-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="acee1-107">[in] Ein `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="acee1-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="acee1-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Zeile.</span><span class="sxs-lookup"><span data-stu-id="acee1-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="acee1-109">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Spalte.</span><span class="sxs-lookup"><span data-stu-id="acee1-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="acee1-110">[out] Ein Zeiger auf eine `ULONG32` , die die Endzeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="acee1-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="acee1-111">[out] Ein Zeiger auf eine `ULONG32` , die die Endspalte empfängt.</span><span class="sxs-lookup"><span data-stu-id="acee1-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="acee1-112">[out] Ein Zeiger auf eine `ULONG32` , die den zugeordneten Sequenzpunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="acee1-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acee1-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="acee1-113">Return Value</span></span>  
 <span data-ttu-id="acee1-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="acee1-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acee1-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acee1-115">Requirements</span></span>  
 <span data-ttu-id="acee1-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="acee1-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acee1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acee1-117">See Also</span></span>  
 [<span data-ttu-id="acee1-118">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acee1-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
