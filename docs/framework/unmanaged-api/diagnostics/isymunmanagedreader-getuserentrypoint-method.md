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
ms.openlocfilehash: 0267ae8b57c837b097d496c8e119085d03417e36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211269"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="798f9-102">ISymUnmanagedReader::GetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="798f9-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="798f9-103">Gibt die Methode, die als benutzerdefinierter Einstiegspunkt für das Modul angegeben wurden, zurück, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="798f9-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="798f9-104">Diese Methode kann z. B. vom Compiler generierten Stubs vor der main-Methode, statt des Benutzers main-Methode sein.</span><span class="sxs-lookup"><span data-stu-id="798f9-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="798f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="798f9-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="798f9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="798f9-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="798f9-107">[out] Ein Zeiger auf eine Variable, die den Einstiegspunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="798f9-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="798f9-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="798f9-108">Return Value</span></span>  
 <span data-ttu-id="798f9-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="798f9-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="798f9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="798f9-110">Requirements</span></span>  
 <span data-ttu-id="798f9-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="798f9-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="798f9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="798f9-112">See also</span></span>

- [<span data-ttu-id="798f9-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798f9-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
