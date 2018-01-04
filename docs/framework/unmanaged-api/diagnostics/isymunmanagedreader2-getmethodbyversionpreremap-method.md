---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0745428c6e9a51c5c7fa413838cf65eb907eea8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="5cbf7-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="5cbf7-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="5cbf7-103">Ruft ein Methodenobjekt des Symbolreaders, erhält ein Methodentoken und eine Versionsnummer mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5cbf7-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="5cbf7-104">Versionsnummern beginnen bei 1 und werden jedes Mal inkrementiert, wenn die Methode als Ergebnis eines Vorgangs bearbeiten und Fortfahren geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5cbf7-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cbf7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cbf7-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cbf7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5cbf7-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="5cbf7-107">[in] Das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="5cbf7-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="5cbf7-108">[in] Die Methodenversion.</span><span class="sxs-lookup"><span data-stu-id="5cbf7-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5cbf7-109">[out] Ein Zeiger auf das zurückgegebene [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5cbf7-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cbf7-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5cbf7-110">Return Value</span></span>  
 <span data-ttu-id="5cbf7-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5cbf7-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cbf7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5cbf7-112">Requirements</span></span>  
 <span data-ttu-id="5cbf7-113">**Header:** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="5cbf7-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="5cbf7-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5cbf7-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbf7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cbf7-115">See Also</span></span>  
 [<span data-ttu-id="5cbf7-116">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5cbf7-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
