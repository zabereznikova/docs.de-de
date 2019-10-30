---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 004e1ddae8a6c0262846422a2eeb4314a4c82f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121613"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="41976-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="41976-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="41976-103">Öffnen Sie einen speziellen benutzerdefinierten Daten Abschnitt, um die Informationen zur Zuordnung von Token zu Quell Informationen in zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="41976-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="41976-104">Wenn Sie diesen Abschnitt öffnen, wenn eine Methode bereits geöffnet ist (oder umgekehrt), ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="41976-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41976-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="41976-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="41976-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="41976-106">Return Value</span></span>  
 <span data-ttu-id="41976-107">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="41976-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41976-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41976-108">Requirements</span></span>  
 <span data-ttu-id="41976-109">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="41976-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41976-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41976-110">See also</span></span>

- [<span data-ttu-id="41976-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41976-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
