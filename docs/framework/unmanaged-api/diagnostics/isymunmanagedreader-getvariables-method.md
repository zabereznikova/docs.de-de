---
title: ISymUnmanagedReader::GetVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 846ff76fb1073394cc27597c9a2015148581cc70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165099"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="f82a5-102">ISymUnmanagedReader::GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="f82a5-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="f82a5-103">Gibt eine nicht lokale Variable mit dem anhand des übergeordneten Elements und dem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="f82a5-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f82a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f82a5-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f82a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f82a5-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="f82a5-106">[in] Das übergeordnete Element der Variablen.</span><span class="sxs-lookup"><span data-stu-id="f82a5-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="f82a5-107">[in] Die Größe des `pVars`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="f82a5-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="f82a5-108">[out] Ein Zeiger auf die Variable, die Anzahl der Variablen, die in zurückgegebenen empfängt `pVars`.</span><span class="sxs-lookup"><span data-stu-id="f82a5-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="f82a5-109">[out] Ein Zeiger auf die Variable, die Variablen empfängt.</span><span class="sxs-lookup"><span data-stu-id="f82a5-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f82a5-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f82a5-110">Return Value</span></span>  
 <span data-ttu-id="f82a5-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f82a5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f82a5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f82a5-112">Requirements</span></span>  
 <span data-ttu-id="f82a5-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f82a5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82a5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f82a5-114">See also</span></span>

- [<span data-ttu-id="f82a5-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f82a5-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
