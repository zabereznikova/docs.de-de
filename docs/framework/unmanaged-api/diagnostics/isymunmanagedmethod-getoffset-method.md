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
ms.openlocfilehash: 358f3d3d7c231a2baa9d2c467935ba3a5867e36b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614473"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="171ec-102">ISymUnmanagedMethod::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="171ec-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="171ec-103">Gibt den Offset innerhalb dieser Methode zurück, der einer bestimmten Position in einem Dokument entspricht.</span><span class="sxs-lookup"><span data-stu-id="171ec-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="171ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="171ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="171ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="171ec-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="171ec-106">in Ein Zeiger auf das Dokument, für das der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="171ec-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="171ec-107">in Die Dokument Zeile, für die der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="171ec-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="171ec-108">in Die Dokument Spalte, für die der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="171ec-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="171ec-109">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Offsets empfängt.</span><span class="sxs-lookup"><span data-stu-id="171ec-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="171ec-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="171ec-110">Return Value</span></span>  
 <span data-ttu-id="171ec-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="171ec-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="171ec-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="171ec-112">Requirements</span></span>  
 <span data-ttu-id="171ec-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="171ec-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="171ec-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="171ec-114">See also</span></span>

- [<span data-ttu-id="171ec-115">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="171ec-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
