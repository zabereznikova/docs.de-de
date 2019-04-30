---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 494f39855132bc4a9551b78f746517862d285034
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940269"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="c2ca3-102">ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="c2ca3-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="c2ca3-103">Ruft den Dateinamen für die Zeile, die ein Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2ca3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2ca3-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2ca3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2ca3-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="c2ca3-106">[in] Ein `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c2ca3-107">[in] Ein `ULONG32` , der angibt, dass der Größe des der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c2ca3-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Dateinamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="c2ca3-109">[out] Der Puffer, der die Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2ca3-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c2ca3-110">Return Value</span></span>  
 <span data-ttu-id="c2ca3-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c2ca3-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2ca3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2ca3-112">Requirements</span></span>  
 <span data-ttu-id="c2ca3-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2ca3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ca3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2ca3-114">See also</span></span>

- [<span data-ttu-id="c2ca3-115">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2ca3-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
