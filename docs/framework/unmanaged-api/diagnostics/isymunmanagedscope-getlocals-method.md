---
title: ISymUnmanagedScope::GetLocals-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 625609d8632f1f73ee2ec01e3b2e0e1af7e4a134
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085713"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="c08cc-102">ISymUnmanagedScope::GetLocals-Methode</span><span class="sxs-lookup"><span data-stu-id="c08cc-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="c08cc-103">Ruft ab, die lokalen Variablen, die innerhalb dieses Bereichs definiert.</span><span class="sxs-lookup"><span data-stu-id="c08cc-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c08cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c08cc-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c08cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c08cc-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="c08cc-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `locals` Array.</span><span class="sxs-lookup"><span data-stu-id="c08cc-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="c08cc-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die lokalen Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c08cc-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="c08cc-108">[out] Das Array, das die lokalen Variablen empfängt.</span><span class="sxs-lookup"><span data-stu-id="c08cc-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c08cc-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c08cc-109">Return Value</span></span>  
 <span data-ttu-id="c08cc-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c08cc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c08cc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c08cc-111">Requirements</span></span>  
 <span data-ttu-id="c08cc-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c08cc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08cc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c08cc-113">See also</span></span>

- [<span data-ttu-id="c08cc-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c08cc-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
