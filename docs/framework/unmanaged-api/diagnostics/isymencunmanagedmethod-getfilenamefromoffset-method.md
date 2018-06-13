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
ms.openlocfilehash: db3e9cfa73672920ff70d9128541a8f513fca00f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432655"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="e53de-102">ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="e53de-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="e53de-103">Ruft den Dateinamen für die Zeile mit einem Versatz verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="e53de-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e53de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e53de-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e53de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e53de-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="e53de-106">[in] Ein `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="e53de-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e53de-107">[in] Ein `ULONG32` , der angibt, dass der Größe des der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="e53de-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e53de-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Dateinamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e53de-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="e53de-109">[out] Der Puffer, der den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="e53de-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e53de-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e53de-110">Return Value</span></span>  
 <span data-ttu-id="e53de-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e53de-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e53de-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e53de-112">Requirements</span></span>  
 <span data-ttu-id="e53de-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e53de-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e53de-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e53de-114">See Also</span></span>  
 [<span data-ttu-id="e53de-115">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e53de-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
