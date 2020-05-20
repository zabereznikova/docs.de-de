---
title: ISymUnmanagedENCUpdate::GetLocalVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 5e5bf097a4b1e366fff807595b22c4696a91cf43
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614551"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="8f404-102">ISymUnmanagedENCUpdate::GetLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="8f404-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="8f404-103">Ruft die lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="8f404-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f404-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f404-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f404-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f404-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="8f404-106">in Das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="8f404-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="8f404-107">in Eine `ULONG` , die die Größe des `rgLocals` Parameters angibt.</span><span class="sxs-lookup"><span data-stu-id="8f404-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="8f404-108">vorgenommen Das zurückgegebene Array von [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="8f404-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8f404-109">vorgenommen Ein Zeiger auf einen `ULONG` , der die Größe des Puffers empfängt, der `rgLocals` zum enthalten der lokalen Variablen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8f404-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f404-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f404-110">Return Value</span></span>  
 <span data-ttu-id="8f404-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8f404-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f404-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f404-112">Requirements</span></span>  
 <span data-ttu-id="8f404-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="8f404-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f404-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f404-114">See also</span></span>

- [<span data-ttu-id="8f404-115">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f404-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
