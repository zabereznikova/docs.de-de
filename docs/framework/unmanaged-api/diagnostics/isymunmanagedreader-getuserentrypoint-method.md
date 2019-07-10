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
ms.openlocfilehash: 995c7edf99c917b8bcdc1d51dcc0bf50868e4f35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777054"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="4a3ee-102">ISymUnmanagedReader::GetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="4a3ee-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="4a3ee-103">Gibt die Methode, die als benutzerdefinierter Einstiegspunkt für das Modul angegeben wurden, zurück, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="4a3ee-104">Diese Methode kann z. B. vom Compiler generierten Stubs vor der main-Methode, statt des Benutzers main-Methode sein.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a3ee-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a3ee-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a3ee-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a3ee-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="4a3ee-107">[out] Ein Zeiger auf eine Variable, die den Einstiegspunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a3ee-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4a3ee-108">Return Value</span></span>  
 <span data-ttu-id="4a3ee-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a3ee-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a3ee-110">Requirements</span></span>  
 <span data-ttu-id="4a3ee-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4a3ee-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a3ee-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a3ee-112">See also</span></span>

- [<span data-ttu-id="4a3ee-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a3ee-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
