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
ms.openlocfilehash: ea0cba1f1b9154ccb14d75f7c377a8153c24f2b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499480"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="80cdc-102">ISymUnmanagedReader::GetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="80cdc-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="80cdc-103">Gibt die Methode, die als benutzerdefinierter Einstiegspunkt für das Modul angegeben wurden, zurück, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="80cdc-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="80cdc-104">Diese Methode kann z. B. vom Compiler generierten Stubs vor der main-Methode, statt des Benutzers main-Methode sein.</span><span class="sxs-lookup"><span data-stu-id="80cdc-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80cdc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="80cdc-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80cdc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="80cdc-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="80cdc-107">[out] Ein Zeiger auf eine Variable, die den Einstiegspunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="80cdc-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80cdc-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80cdc-108">Return Value</span></span>  
 <span data-ttu-id="80cdc-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="80cdc-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80cdc-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80cdc-110">Requirements</span></span>  
 <span data-ttu-id="80cdc-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="80cdc-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cdc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80cdc-112">See also</span></span>
- [<span data-ttu-id="80cdc-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80cdc-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
