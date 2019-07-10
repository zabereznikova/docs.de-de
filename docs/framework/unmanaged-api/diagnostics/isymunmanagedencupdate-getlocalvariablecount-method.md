---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d56785815105e2f4b06217d3375e2d1cfdf0494c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776910"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="8e5ad-102">ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="8e5ad-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="8e5ad-103">Ruft die Anzahl der lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="8e5ad-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e5ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e5ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e5ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e5ad-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="8e5ad-106">[in] Das Metadatentoken der Methoden.</span><span class="sxs-lookup"><span data-stu-id="8e5ad-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="8e5ad-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Anzahl der lokalen Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e5ad-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e5ad-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8e5ad-108">Return Value</span></span>  
 <span data-ttu-id="8e5ad-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8e5ad-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e5ad-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e5ad-110">Requirements</span></span>  
 <span data-ttu-id="8e5ad-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8e5ad-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5ad-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e5ad-112">See also</span></span>

- [<span data-ttu-id="8e5ad-113">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e5ad-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
