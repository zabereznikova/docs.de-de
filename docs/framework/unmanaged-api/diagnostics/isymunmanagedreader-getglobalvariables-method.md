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
ms.openlocfilehash: 299787ea4eb8a5c25bdab64ad08445839c9f24d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707541"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="2f72c-102">ISymUnmanagedReader::GetGlobalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="2f72c-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>

<span data-ttu-id="2f72c-103">Gibt alle globalen Variablen zurück.</span><span class="sxs-lookup"><span data-stu-id="2f72c-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f72c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f72c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f72c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f72c-105">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="2f72c-106">in Die Länge des Puffers, auf den verweist `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="2f72c-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="2f72c-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Variablen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2f72c-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="2f72c-108">vorgenommen Ein Puffer, der die Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="2f72c-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f72c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2f72c-109">Return Value</span></span>  

 <span data-ttu-id="2f72c-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2f72c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f72c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2f72c-111">Requirements</span></span>  

 <span data-ttu-id="2f72c-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2f72c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f72c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f72c-113">See also</span></span>

- [<span data-ttu-id="2f72c-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f72c-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
