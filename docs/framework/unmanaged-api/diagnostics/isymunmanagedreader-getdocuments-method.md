---
title: ISymUnmanagedReader::GetDocuments-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: 757b7fecbbb187da079c8a5c51462ec58431966f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707619"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="84339-102">ISymUnmanagedReader::GetDocuments-Methode</span><span class="sxs-lookup"><span data-stu-id="84339-102">ISymUnmanagedReader::GetDocuments Method</span></span>

<span data-ttu-id="84339-103">Gibt ein Array aller im Symbol Speicher definierten Dokumente zurück.</span><span class="sxs-lookup"><span data-stu-id="84339-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84339-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84339-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84339-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84339-105">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="84339-106">[in] Die Größe des `pDocs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="84339-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="84339-107">vorgenommen Ein Zeiger auf eine Variable, die die Array Länge empfängt.</span><span class="sxs-lookup"><span data-stu-id="84339-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="84339-108">vorgenommen Ein Zeiger auf eine Variable, die das Dokument Array empfängt.</span><span class="sxs-lookup"><span data-stu-id="84339-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84339-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84339-109">Return Value</span></span>  

 <span data-ttu-id="84339-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="84339-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84339-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="84339-111">Requirements</span></span>  

 <span data-ttu-id="84339-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="84339-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84339-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84339-113">See also</span></span>

- [<span data-ttu-id="84339-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84339-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
