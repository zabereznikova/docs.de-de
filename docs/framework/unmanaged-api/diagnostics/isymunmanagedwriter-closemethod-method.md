---
title: ISymUnmanagedWriter::CloseMethod-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f77f30b84622dffd8c76bb9302ad564f40ed41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778186"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="60255-102">ISymUnmanagedWriter::CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="60255-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="60255-103">Schließt die aktuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="60255-103">Closes the current method.</span></span> <span data-ttu-id="60255-104">Sobald eine Methode geschlossen wurde, können keine Symbole mehr darin definiert werden.</span><span class="sxs-lookup"><span data-stu-id="60255-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60255-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="60255-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="60255-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60255-106">Return Value</span></span>  
 <span data-ttu-id="60255-107">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="60255-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60255-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60255-108">Requirements</span></span>  
 <span data-ttu-id="60255-109">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="60255-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60255-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60255-110">See also</span></span>

- [<span data-ttu-id="60255-111">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60255-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="60255-112">OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="60255-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
