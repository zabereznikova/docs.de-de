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
ms.openlocfilehash: 9ec44d4c2757555c74fe7fc27c26cc5fc87c4517
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426686"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="e23cf-102">ISymUnmanagedWriter::SetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="e23cf-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="e23cf-103">Gibt die benutzerdefinierte Methode, die den Einstiegspunkt für dieses Modul ist.</span><span class="sxs-lookup"><span data-stu-id="e23cf-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="e23cf-104">Beispielsweise könnte diesen Einstiegspunkt main-Methode des Benutzers anstelle von vom Compiler generierte Stubs vor Main sein.</span><span class="sxs-lookup"><span data-stu-id="e23cf-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e23cf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e23cf-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e23cf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e23cf-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="e23cf-107">[in] Zeigen Sie das Metadatentoken für die Methode, die der benutzerdefinierte Einstiegspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="e23cf-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e23cf-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e23cf-108">Return Value</span></span>  
 <span data-ttu-id="e23cf-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e23cf-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e23cf-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e23cf-110">Requirements</span></span>  
 <span data-ttu-id="e23cf-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e23cf-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e23cf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e23cf-112">See Also</span></span>  
 [<span data-ttu-id="e23cf-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e23cf-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
