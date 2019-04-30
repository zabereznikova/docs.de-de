---
title: ISymENCUnmanagedMethod::GetLineFromOffset-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3106c6680750826306cffb31e599ee2260bf4ad7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940295"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="0cca4-102">ISymENCUnmanagedMethod::GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="0cca4-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="0cca4-103">Ruft die Zeileninformationen, die ein Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0cca4-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="0cca4-104">Wenn der Offsetparameter (`dwOffset`) ein Sequenzpunkt ist diese Methode ruft die Zeileninformationen ab dem Offset des vorherigen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0cca4-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cca4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cca4-105">Syntax</span></span>  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cca4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cca4-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="0cca4-107">[in] Ein `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="0cca4-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="0cca4-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Zeile.</span><span class="sxs-lookup"><span data-stu-id="0cca4-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="0cca4-109">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Spalte.</span><span class="sxs-lookup"><span data-stu-id="0cca4-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="0cca4-110">[out] Ein Zeiger auf eine `ULONG32` , empfängt die letzte Zeile.</span><span class="sxs-lookup"><span data-stu-id="0cca4-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="0cca4-111">[out] Ein Zeiger auf eine `ULONG32` , empfängt die letzte Spalte.</span><span class="sxs-lookup"><span data-stu-id="0cca4-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="0cca4-112">[out] Ein Zeiger auf eine `ULONG32` , das den zugeordneten Sequenzpunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="0cca4-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cca4-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0cca4-113">Return Value</span></span>  
 <span data-ttu-id="0cca4-114">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0cca4-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cca4-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cca4-115">Requirements</span></span>  
 <span data-ttu-id="0cca4-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0cca4-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cca4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cca4-117">See also</span></span>

- [<span data-ttu-id="0cca4-118">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cca4-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
