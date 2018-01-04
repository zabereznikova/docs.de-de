---
title: ISymUnmanagedWriter::SetUserEntryPoint-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetUserEntryPoint
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5da021bce46df02789547eb7ee50133b6f4d4af6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="0c35d-102">ISymUnmanagedWriter::SetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="0c35d-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="0c35d-103">Gibt die benutzerdefinierte Methode, die den Einstiegspunkt für dieses Modul ist.</span><span class="sxs-lookup"><span data-stu-id="0c35d-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="0c35d-104">Beispielsweise könnte diesen Einstiegspunkt main-Methode des Benutzers anstelle von vom Compiler generierte Stubs vor Main sein.</span><span class="sxs-lookup"><span data-stu-id="0c35d-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c35d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c35d-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c35d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c35d-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="0c35d-107">[in] Zeigen Sie das Metadatentoken für die Methode, die der benutzerdefinierte Einstiegspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="0c35d-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c35d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0c35d-108">Return Value</span></span>  
 <span data-ttu-id="0c35d-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0c35d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c35d-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c35d-110">Requirements</span></span>  
 <span data-ttu-id="0c35d-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0c35d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c35d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c35d-112">See Also</span></span>  
 [<span data-ttu-id="0c35d-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c35d-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
