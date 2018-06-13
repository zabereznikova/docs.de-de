---
title: ISymUnmanagedScope::GetEndOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d13006bc5c09ed065ae1671ee75cf8dce066669d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426302"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="d942c-102">ISymUnmanagedScope::GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="d942c-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="d942c-103">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="d942c-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d942c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d942c-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d942c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d942c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d942c-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt den Endoffset.</span><span class="sxs-lookup"><span data-stu-id="d942c-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d942c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d942c-107">Return Value</span></span>  
 <span data-ttu-id="d942c-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d942c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d942c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d942c-109">Requirements</span></span>  
 <span data-ttu-id="d942c-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d942c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d942c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d942c-111">See Also</span></span>  
 [<span data-ttu-id="d942c-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d942c-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="d942c-113">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="d942c-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
