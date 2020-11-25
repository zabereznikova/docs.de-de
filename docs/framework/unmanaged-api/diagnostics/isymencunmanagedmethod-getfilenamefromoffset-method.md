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
ms.openlocfilehash: ad9631039c8d032e7ffdba1e6098b66398f82277
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707385"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="bb95e-102">ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="bb95e-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>

<span data-ttu-id="bb95e-103">Ruft den Dateinamen für die Zeile ab, die einem Offset zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bb95e-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb95e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb95e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb95e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb95e-105">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="bb95e-106">in Ein-Wert `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="bb95e-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="bb95e-107">in Eine `ULONG32` , die die Größe des `szName` Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="bb95e-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="bb95e-108">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Dateinamen enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="bb95e-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="bb95e-109">vorgenommen Der Puffer, der die Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="bb95e-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb95e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb95e-110">Return Value</span></span>  

 <span data-ttu-id="bb95e-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="bb95e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb95e-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bb95e-112">Requirements</span></span>  

 <span data-ttu-id="bb95e-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="bb95e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb95e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb95e-114">See also</span></span>

- [<span data-ttu-id="bb95e-115">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb95e-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
