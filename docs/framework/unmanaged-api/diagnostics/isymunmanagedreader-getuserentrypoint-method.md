---
title: ISymUnmanagedReader::GetUserEntryPoint-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8519577bb2b9d3ff8fa2138ba007d04d9fde159
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730151"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="9daf0-102">ISymUnmanagedReader::GetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="9daf0-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="9daf0-103">Gibt die Methode, die als benutzerdefinierter Einstiegspunkt für das Modul angegeben wurden, zurück, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9daf0-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="9daf0-104">Diese Methode kann z. B. vom Compiler generierten Stubs vor der main-Methode, statt des Benutzers main-Methode sein.</span><span class="sxs-lookup"><span data-stu-id="9daf0-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9daf0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9daf0-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9daf0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9daf0-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="9daf0-107">[out] Ein Zeiger auf eine Variable, die den Einstiegspunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="9daf0-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9daf0-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9daf0-108">Return Value</span></span>  
 <span data-ttu-id="9daf0-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9daf0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9daf0-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9daf0-110">Requirements</span></span>  
 <span data-ttu-id="9daf0-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9daf0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9daf0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9daf0-112">See also</span></span>
- [<span data-ttu-id="9daf0-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9daf0-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
