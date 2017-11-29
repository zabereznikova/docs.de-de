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
ms.openlocfilehash: 7b5e4fa5fcdb41126b827ee157230d79e07ed977
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="e56cd-102">ISymUnmanagedMethod::GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="e56cd-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="e56cd-103">Ruft die Anfangs- und Enddatum Dokumentpositionen für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="e56cd-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="e56cd-104">Die Arrayposition des erste dient als Startpunkt für, und die zweite Arrayposition wird am Ende.</span><span class="sxs-lookup"><span data-stu-id="e56cd-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56cd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e56cd-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e56cd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e56cd-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="e56cd-107">[in] Das Anfangs- und Endquelldokumente.</span><span class="sxs-lookup"><span data-stu-id="e56cd-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="e56cd-108">[in] Die Anfangs- und Endzeilen in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="e56cd-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="e56cd-109">[in] Die Anfangs- und Endspalten in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="e56cd-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e56cd-110">[out] `true` wenn Positionen definiert; andernfalls wurden, `false`.</span><span class="sxs-lookup"><span data-stu-id="e56cd-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e56cd-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e56cd-111">Return Value</span></span>  
 <span data-ttu-id="e56cd-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e56cd-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e56cd-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e56cd-113">Requirements</span></span>  
 <span data-ttu-id="e56cd-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e56cd-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e56cd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e56cd-115">See Also</span></span>  
 [<span data-ttu-id="e56cd-116">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e56cd-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
