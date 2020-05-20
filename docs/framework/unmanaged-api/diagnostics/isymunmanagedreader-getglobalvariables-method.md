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
ms.openlocfilehash: 20bfb3e48f411524bd4d9798f17dd935595a12bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615019"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="0275d-102">ISymUnmanagedReader::GetGlobalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="0275d-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="0275d-103">Gibt alle globalen Variablen zurück.</span><span class="sxs-lookup"><span data-stu-id="0275d-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0275d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0275d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0275d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0275d-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="0275d-106">in Die Länge des Puffers, auf den verweist `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="0275d-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="0275d-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Variablen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0275d-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="0275d-108">vorgenommen Ein Puffer, der die Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="0275d-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0275d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0275d-109">Return Value</span></span>  
 <span data-ttu-id="0275d-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0275d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0275d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0275d-111">Requirements</span></span>  
 <span data-ttu-id="0275d-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0275d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0275d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0275d-113">See also</span></span>

- [<span data-ttu-id="0275d-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0275d-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
