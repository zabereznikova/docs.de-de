---
title: ISymUnmanagedWriter::CloseNamespace-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4429d49a489871a8993d9f841d9c5e7e37a53b5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689678"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="e4250-102">ISymUnmanagedWriter::CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="e4250-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="e4250-103">Den zuletzt geöffneten schließt Namespace.</span><span class="sxs-lookup"><span data-stu-id="e4250-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4250-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4250-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e4250-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e4250-105">Return Value</span></span>  
 <span data-ttu-id="e4250-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e4250-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4250-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4250-107">Requirements</span></span>  
 <span data-ttu-id="e4250-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e4250-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4250-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4250-109">See also</span></span>
- [<span data-ttu-id="e4250-110">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4250-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e4250-111">OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="e4250-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
