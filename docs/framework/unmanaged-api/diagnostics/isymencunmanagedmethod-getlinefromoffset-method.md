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
ms.openlocfilehash: d9a7b18e90a3038c1ffb634ccc7315143875c809
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441915"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="f068a-102">ISymENCUnmanagedMethod::GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="f068a-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="f068a-103">Ruft die einem Offset zugeordneten Zeilen Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="f068a-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="f068a-104">Wenn der Offset Parameter ( `dwOffset` ) kein Sequenz Punkt ist, ruft diese Methode die dem vorherigen Offset zugeordneten Zeilen Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="f068a-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f068a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f068a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f068a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f068a-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="f068a-107">in Ein-Wert `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="f068a-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="f068a-108">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Zeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="f068a-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="f068a-109">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Spalte empfängt.</span><span class="sxs-lookup"><span data-stu-id="f068a-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="f068a-110">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Endzeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="f068a-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="f068a-111">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Endspalte empfängt.</span><span class="sxs-lookup"><span data-stu-id="f068a-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="f068a-112">vorgenommen Ein Zeiger auf einen `ULONG32` , der den zugeordneten Sequenz Punkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="f068a-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f068a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f068a-113">Return Value</span></span>  
 <span data-ttu-id="f068a-114">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f068a-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f068a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f068a-115">Requirements</span></span>  
 <span data-ttu-id="f068a-116">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="f068a-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f068a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f068a-117">See also</span></span>

- [<span data-ttu-id="f068a-118">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f068a-118">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
