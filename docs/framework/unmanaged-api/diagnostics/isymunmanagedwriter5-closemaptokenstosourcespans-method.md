---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5f23c3fe39adcebcfdfadb9e9c2b639f16330d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="4d2e2-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="4d2e2-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="4d2e2-103">Schließen Sie die spezielle benutzerdefinierte Datenabschnitt für Token-Source-Spanne Zuordnungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="4d2e2-104">Nachdem sie geschlossen wurde, kann keine weiteren Zuordnungsinformationen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2e2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d2e2-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4d2e2-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4d2e2-106">Return Value</span></span>  
 <span data-ttu-id="4d2e2-107">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d2e2-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d2e2-108">Requirements</span></span>  
 <span data-ttu-id="4d2e2-109">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4d2e2-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2e2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d2e2-110">See Also</span></span>  
 [<span data-ttu-id="4d2e2-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d2e2-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
