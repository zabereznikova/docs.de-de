---
title: ISymUnmanagedMethod::GetSourceStartEnd-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetSourceStartEnd
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2bdc044d4560b616bd6eeb8d642567add1f659f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="ef249-102">ISymUnmanagedMethod::GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="ef249-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="ef249-103">Ruft die Anfangs- und Enddatum Dokumentpositionen für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="ef249-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="ef249-104">Die Arrayposition des erste dient als Startpunkt für, und die zweite Arrayposition wird am Ende.</span><span class="sxs-lookup"><span data-stu-id="ef249-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef249-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef249-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef249-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef249-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="ef249-107">[in] Das Anfangs- und Endquelldokumente.</span><span class="sxs-lookup"><span data-stu-id="ef249-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="ef249-108">[in] Die Anfangs- und Endzeilen in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="ef249-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="ef249-109">[in] Die Anfangs- und Endspalten in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="ef249-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ef249-110">[out] `true` wenn Positionen definiert; andernfalls wurden, `false`.</span><span class="sxs-lookup"><span data-stu-id="ef249-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef249-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ef249-111">Return Value</span></span>  
 <span data-ttu-id="ef249-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ef249-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef249-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef249-113">Requirements</span></span>  
 <span data-ttu-id="ef249-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ef249-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef249-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef249-115">See Also</span></span>  
 [<span data-ttu-id="ef249-116">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef249-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
