---
title: ISymUnmanagedReader::GetMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab6228866434b35525b16e97b8cba718b849dea1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213206"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="5ff15-102">ISymUnmanagedReader::GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5ff15-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="5ff15-103">Ruft ein Methodenobjekt des Symbolreaders, mit dem angegebenen ein Methodentoken ab.</span><span class="sxs-lookup"><span data-stu-id="5ff15-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ff15-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff15-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ff15-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="5ff15-106">[in] Das Methodentoken.</span><span class="sxs-lookup"><span data-stu-id="5ff15-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5ff15-107">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5ff15-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ff15-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5ff15-108">Return Value</span></span>  
 <span data-ttu-id="5ff15-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5ff15-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff15-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ff15-110">Requirements</span></span>  
 <span data-ttu-id="5ff15-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5ff15-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff15-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ff15-112">See also</span></span>

- [<span data-ttu-id="5ff15-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ff15-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
