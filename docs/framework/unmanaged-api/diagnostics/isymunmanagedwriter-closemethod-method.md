---
title: ISymUnmanagedWriter::CloseMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21c4cdd42613f5e8b60c39426b4f169a034ce7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="91a9b-102">ISymUnmanagedWriter::CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="91a9b-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="91a9b-103">Schließt die aktuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="91a9b-103">Closes the current method.</span></span> <span data-ttu-id="91a9b-104">Nachdem eine Methode geschlossen wurde, können keine weitere Symbole darin definiert werden.</span><span class="sxs-lookup"><span data-stu-id="91a9b-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a9b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="91a9b-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="91a9b-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="91a9b-106">Return Value</span></span>  
 <span data-ttu-id="91a9b-107">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="91a9b-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a9b-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91a9b-108">Requirements</span></span>  
 <span data-ttu-id="91a9b-109">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="91a9b-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a9b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91a9b-110">See Also</span></span>  
 [<span data-ttu-id="91a9b-111">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91a9b-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="91a9b-112">OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="91a9b-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
