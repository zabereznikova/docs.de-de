---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 95976e2f331252c88eab717e184abc284842e3b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683263"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="2e0f3-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="2e0f3-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="2e0f3-103">Öffnen Sie einen speziellen benutzerdefinierten Daten Abschnitt, um die Informationen zur Zuordnung von Token zu Quell Informationen in zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="2e0f3-104">Wenn Sie diesen Abschnitt öffnen, wenn eine Methode bereits geöffnet ist (oder umgekehrt), ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e0f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e0f3-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2e0f3-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2e0f3-106">Return Value</span></span>  

 <span data-ttu-id="2e0f3-107">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e0f3-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2e0f3-108">Requirements</span></span>  

 <span data-ttu-id="2e0f3-109">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2e0f3-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0f3-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e0f3-110">See also</span></span>

- [<span data-ttu-id="2e0f3-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e0f3-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
