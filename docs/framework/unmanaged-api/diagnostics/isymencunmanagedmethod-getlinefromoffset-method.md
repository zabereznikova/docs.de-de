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
ms.openlocfilehash: 196993df9058d3eb8167e0144255c5fe366c54f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707359"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="f1910-102">ISymENCUnmanagedMethod::GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="f1910-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>

<span data-ttu-id="f1910-103">Ruft die einem Offset zugeordneten Zeilen Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="f1910-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="f1910-104">Wenn der Offset Parameter ( `dwOffset` ) kein Sequenz Punkt ist, ruft diese Methode die dem vorherigen Offset zugeordneten Zeilen Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="f1910-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1910-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1910-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1910-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1910-106">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="f1910-107">in Ein-Wert `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="f1910-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="f1910-108">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Zeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="f1910-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="f1910-109">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Spalte empfängt.</span><span class="sxs-lookup"><span data-stu-id="f1910-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="f1910-110">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Endzeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="f1910-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="f1910-111">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Endspalte empfängt.</span><span class="sxs-lookup"><span data-stu-id="f1910-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="f1910-112">vorgenommen Ein Zeiger auf einen `ULONG32` , der den zugeordneten Sequenz Punkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="f1910-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1910-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f1910-113">Return Value</span></span>  

 <span data-ttu-id="f1910-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f1910-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1910-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1910-115">Requirements</span></span>  

 <span data-ttu-id="f1910-116">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="f1910-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1910-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1910-117">See also</span></span>

- [<span data-ttu-id="f1910-118">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1910-118">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
