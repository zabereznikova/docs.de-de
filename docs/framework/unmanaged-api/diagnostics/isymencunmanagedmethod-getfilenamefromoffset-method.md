---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9dcdbf7813c7ce3d451a27c0abf08c661a8f17b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="ecdeb-102">ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ecdeb-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="ecdeb-103">Ruft den Dateinamen für die Zeile mit einem Versatz verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ecdeb-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdeb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecdeb-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecdeb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecdeb-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="ecdeb-106">[in] Ein `ULONG32` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="ecdeb-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ecdeb-107">[in] Ein `ULONG32` , der angibt, dass der Größe des der `szName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="ecdeb-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ecdeb-108">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Dateinamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ecdeb-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="ecdeb-109">[out] Der Puffer, der den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="ecdeb-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecdeb-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ecdeb-110">Return Value</span></span>  
 <span data-ttu-id="ecdeb-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ecdeb-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecdeb-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecdeb-112">Requirements</span></span>  
 <span data-ttu-id="ecdeb-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ecdeb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecdeb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecdeb-114">See Also</span></span>  
 [<span data-ttu-id="ecdeb-115">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecdeb-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
