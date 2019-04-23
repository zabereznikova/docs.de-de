---
title: ISymUnmanagedMethod::GetOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a42dc624d4de9cddebad287f6d90590f96b30272
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223653"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="e0e72-102">ISymUnmanagedMethod::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="e0e72-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="e0e72-103">Gibt den Offset innerhalb dieser Methode entspricht, die an einer bestimmten Position in einem Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="e0e72-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e72-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0e72-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0e72-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0e72-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="e0e72-106">[in] Ein Zeiger auf das Dokument, das für das der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="e0e72-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="e0e72-107">[in] Die Dokumentzeile, für die der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="e0e72-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="e0e72-108">[in] Die Dokumentspalte, für die der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="e0e72-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e0e72-109">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Offsets.</span><span class="sxs-lookup"><span data-stu-id="e0e72-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0e72-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e0e72-110">Return Value</span></span>  
 <span data-ttu-id="e0e72-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e0e72-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e72-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0e72-112">Requirements</span></span>  
 <span data-ttu-id="e0e72-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e0e72-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e72-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0e72-114">See also</span></span>

- [<span data-ttu-id="e0e72-115">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0e72-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
