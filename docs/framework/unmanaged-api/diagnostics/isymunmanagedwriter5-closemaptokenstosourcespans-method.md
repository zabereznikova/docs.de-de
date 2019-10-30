---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 43c35596d31842b85bbdc96a63413a176a59a172
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121656"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="aa271-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="aa271-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="aa271-103">Schließen Sie den speziellen benutzerdefinierten Daten Abschnitt für die Übersetzung von Zuordnungsinformationen zwischen Token und Quelle.</span><span class="sxs-lookup"><span data-stu-id="aa271-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="aa271-104">Nachdem Sie geschlossen wurde, können keine weiteren Zuordnungsinformationen mehr hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aa271-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa271-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa271-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="aa271-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa271-106">Return Value</span></span>  
 <span data-ttu-id="aa271-107">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="aa271-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa271-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa271-108">Requirements</span></span>  
 <span data-ttu-id="aa271-109">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="aa271-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa271-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa271-110">See also</span></span>

- [<span data-ttu-id="aa271-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa271-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
