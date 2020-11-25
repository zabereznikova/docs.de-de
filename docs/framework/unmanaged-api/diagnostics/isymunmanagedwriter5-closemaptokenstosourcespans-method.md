---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: b57174f9f76b174927b8f1997beac3dd1482583a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725910"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="6e15b-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="6e15b-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="6e15b-103">Schließen Sie den speziellen benutzerdefinierten Daten Abschnitt für die Übersetzung von Zuordnungsinformationen zwischen Token und Quelle.</span><span class="sxs-lookup"><span data-stu-id="6e15b-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="6e15b-104">Nachdem Sie geschlossen wurde, können keine weiteren Zuordnungsinformationen mehr hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6e15b-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e15b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e15b-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6e15b-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e15b-106">Return Value</span></span>  

 <span data-ttu-id="6e15b-107">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="6e15b-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e15b-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6e15b-108">Requirements</span></span>  

 <span data-ttu-id="6e15b-109">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6e15b-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e15b-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e15b-110">See also</span></span>

- [<span data-ttu-id="6e15b-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e15b-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
