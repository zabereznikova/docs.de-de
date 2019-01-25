---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce4b41854d5d9324169b1873f431ef81c0a4c5be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677917"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="5c7a4-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="5c7a4-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="5c7a4-103">Spezielle benutzerdefinierte Data-Abschnitt für Token-to-Source-Spanne, die Zuordnungsinformationen zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c7a4-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="5c7a4-104">Nachdem sie geschlossen wurde, kann keine weiteren Zuordnungsinformationen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5c7a4-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c7a4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c7a4-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5c7a4-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5c7a4-106">Return Value</span></span>  
 <span data-ttu-id="5c7a4-107">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="5c7a4-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c7a4-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c7a4-108">Requirements</span></span>  
 <span data-ttu-id="5c7a4-109">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5c7a4-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7a4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c7a4-110">See also</span></span>
- [<span data-ttu-id="5c7a4-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c7a4-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
