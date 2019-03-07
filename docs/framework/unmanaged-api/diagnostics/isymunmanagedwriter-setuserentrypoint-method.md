---
title: ISymUnmanagedWriter::SetUserEntryPoint-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bd3d411ad6fe7f65d1eeb25754794704752009e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488356"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="2ca54-102">ISymUnmanagedWriter::SetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="2ca54-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="2ca54-103">Gibt die benutzerdefinierte Methode, die der Einstiegspunkt für dieses Modul ist.</span><span class="sxs-lookup"><span data-stu-id="2ca54-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="2ca54-104">Dieser Einstiegspunkt kann z. B. main-Methode des Benutzers statt vom Compiler generierten Stubs vor Main sein.</span><span class="sxs-lookup"><span data-stu-id="2ca54-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca54-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ca54-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca54-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ca54-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="2ca54-107">[in] Zeigen Sie das Metadatentoken für die Methode, die der benutzerdefinierte Einstiegspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="2ca54-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ca54-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2ca54-108">Return Value</span></span>  
 <span data-ttu-id="2ca54-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2ca54-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca54-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ca54-110">Requirements</span></span>  
 <span data-ttu-id="2ca54-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2ca54-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca54-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca54-112">See also</span></span>
- [<span data-ttu-id="2ca54-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ca54-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
