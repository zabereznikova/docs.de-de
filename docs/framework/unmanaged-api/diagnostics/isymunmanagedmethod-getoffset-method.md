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
ms.openlocfilehash: 14d4211b208482a399aa00430791b3efffda851e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699546"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="61e25-102">ISymUnmanagedMethod::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="61e25-102">ISymUnmanagedMethod::GetOffset Method</span></span>

<span data-ttu-id="61e25-103">Gibt den Offset innerhalb dieser Methode zurück, der einer bestimmten Position in einem Dokument entspricht.</span><span class="sxs-lookup"><span data-stu-id="61e25-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61e25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61e25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61e25-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61e25-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="61e25-106">in Ein Zeiger auf das Dokument, für das der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="61e25-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="61e25-107">in Die Dokument Zeile, für die der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="61e25-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="61e25-108">in Die Dokument Spalte, für die der Offset angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="61e25-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="61e25-109">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Offsets empfängt.</span><span class="sxs-lookup"><span data-stu-id="61e25-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61e25-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61e25-110">Return Value</span></span>  

 <span data-ttu-id="61e25-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="61e25-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61e25-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="61e25-112">Requirements</span></span>  

 <span data-ttu-id="61e25-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="61e25-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e25-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61e25-114">See also</span></span>

- [<span data-ttu-id="61e25-115">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61e25-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
