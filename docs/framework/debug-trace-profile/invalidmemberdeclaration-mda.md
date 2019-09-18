---
title: invalidMemberDeclaration-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe15d718a9c5f91bfae4f37c04e726990e2fbd45
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052587"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="bae2e-102">invalidMemberDeclaration-MDA</span><span class="sxs-lookup"><span data-stu-id="bae2e-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="bae2e-103">Der `invalidMemberDeclaration`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, um einen Fehler zu melden, der aufgetreten ist, als ermittelt werden sollte, wie das Marshalling für die Parameter eines Members zu erfolgen hat, das aus COM aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bae2e-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bae2e-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="bae2e-104">Symptoms</span></span>  
 <span data-ttu-id="bae2e-105">Es wird ein Fehler-HRESULT an COM zurückgegeben, ohne dass die verwaltete Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="bae2e-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bae2e-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="bae2e-106">Cause</span></span>  
 <span data-ttu-id="bae2e-107">Dies wird höchstwahrscheinlich durch ein inkompatibles <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut für einen der Parameter verursacht.</span><span class="sxs-lookup"><span data-stu-id="bae2e-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bae2e-108">Auflösung</span><span class="sxs-lookup"><span data-stu-id="bae2e-108">Resolution</span></span>  
 <span data-ttu-id="bae2e-109">Geben Sie gültige <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribute für die Parameter an.</span><span class="sxs-lookup"><span data-stu-id="bae2e-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bae2e-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bae2e-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="bae2e-111">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="bae2e-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bae2e-112">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="bae2e-112">Output</span></span>  
 <span data-ttu-id="bae2e-113">Eine Informationsmeldung, die den Membernamen, den Typnamen und die Fehlermeldung enthält.</span><span class="sxs-lookup"><span data-stu-id="bae2e-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bae2e-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bae2e-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bae2e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bae2e-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="bae2e-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="bae2e-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bae2e-117">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="bae2e-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
