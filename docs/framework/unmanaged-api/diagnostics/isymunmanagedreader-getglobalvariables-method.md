---
title: ISymUnmanagedReader::GetGlobalVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6574c4d30b963ce571343d1a584bfccb48ffd195
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430450"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="4f724-102">ISymUnmanagedReader::GetGlobalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="4f724-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="4f724-103">Gibt alle globale Variablen zurück.</span><span class="sxs-lookup"><span data-stu-id="4f724-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f724-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f724-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f724-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f724-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="4f724-106">[in] Die Länge des Puffers verweist `pcVars`.</span><span class="sxs-lookup"><span data-stu-id="4f724-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="4f724-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4f724-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="4f724-108">[out] Ein Puffer, der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="4f724-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f724-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4f724-109">Return Value</span></span>  
 <span data-ttu-id="4f724-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4f724-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f724-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f724-111">Requirements</span></span>  
 <span data-ttu-id="4f724-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f724-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f724-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f724-113">See Also</span></span>  
 [<span data-ttu-id="4f724-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f724-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
