---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 82b46ea315009b65254735d44e355154b83b22e2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609494"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="7cb98-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="7cb98-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="7cb98-103">Öffnen Sie einen speziellen benutzerdefinierten Daten Abschnitt, um die Informationen zur Zuordnung von Token zu Quell Informationen in zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="7cb98-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="7cb98-104">Wenn Sie diesen Abschnitt öffnen, wenn eine Methode bereits geöffnet ist (oder umgekehrt), ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7cb98-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cb98-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cb98-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7cb98-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7cb98-106">Return Value</span></span>  
 <span data-ttu-id="7cb98-107">Gibt `HRESULT` zurück.</span><span class="sxs-lookup"><span data-stu-id="7cb98-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cb98-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7cb98-108">Requirements</span></span>  
 <span data-ttu-id="7cb98-109">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="7cb98-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb98-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cb98-110">See also</span></span>

- [<span data-ttu-id="7cb98-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cb98-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
