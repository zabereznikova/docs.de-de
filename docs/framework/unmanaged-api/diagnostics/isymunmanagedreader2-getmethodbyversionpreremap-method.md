---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcd200b7fa431f193dd202c3c2a690aa22ec8e32
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135179"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="431d5-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="431d5-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="431d5-103">Ruft ein Methodenobjekt des Symbolreaders, wenn ein Methodentoken und eine Versionsnummer mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="431d5-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="431d5-104">Versionsnummern beginnen bei 1 und werden jedes Mal inkrementiert, die als Ergebnis eines Vorgangs bearbeiten und Fortfahren die Methode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="431d5-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="431d5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="431d5-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="431d5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="431d5-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="431d5-107">[in] Das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="431d5-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="431d5-108">[in] Die Methodenversion.</span><span class="sxs-lookup"><span data-stu-id="431d5-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="431d5-109">[out] Ein Zeiger auf das zurückgegebene [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="431d5-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="431d5-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="431d5-110">Return Value</span></span>  
 <span data-ttu-id="431d5-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="431d5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="431d5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="431d5-112">Requirements</span></span>  
 <span data-ttu-id="431d5-113">**Header:** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="431d5-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="431d5-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="431d5-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431d5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="431d5-115">See also</span></span>

- [<span data-ttu-id="431d5-116">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="431d5-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
