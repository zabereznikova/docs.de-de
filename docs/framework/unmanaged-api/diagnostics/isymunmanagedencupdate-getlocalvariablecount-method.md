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
ms.openlocfilehash: d7d557e2111a26c0865c20d8eb952c4d42b5604e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436058"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="2abdb-102">ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="2abdb-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="2abdb-103">Ruft die Anzahl der lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="2abdb-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2abdb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2abdb-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2abdb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2abdb-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="2abdb-106">[in] Das Metadatentoken der Methoden.</span><span class="sxs-lookup"><span data-stu-id="2abdb-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="2abdb-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um die Anzahl der lokalen Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2abdb-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2abdb-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2abdb-108">Return Value</span></span>  
 <span data-ttu-id="2abdb-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2abdb-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2abdb-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2abdb-110">Requirements</span></span>  
 <span data-ttu-id="2abdb-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2abdb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2abdb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2abdb-112">See Also</span></span>  
 [<span data-ttu-id="2abdb-113">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2abdb-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
