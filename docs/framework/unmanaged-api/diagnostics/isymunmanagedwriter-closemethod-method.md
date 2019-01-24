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
ms.openlocfilehash: a6f8c8b522aabfce3b83b6b624bd0ca9757448ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666019"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="74365-102">ISymUnmanagedWriter::CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="74365-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="74365-103">Schließt die aktuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="74365-103">Closes the current method.</span></span> <span data-ttu-id="74365-104">Sobald eine Methode geschlossen wurde, können keine Symbole mehr darin definiert werden.</span><span class="sxs-lookup"><span data-stu-id="74365-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74365-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74365-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="74365-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74365-106">Return Value</span></span>  
 <span data-ttu-id="74365-107">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="74365-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74365-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74365-108">Requirements</span></span>  
 <span data-ttu-id="74365-109">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="74365-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74365-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74365-110">See also</span></span>
- [<span data-ttu-id="74365-111">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74365-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="74365-112">OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="74365-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
