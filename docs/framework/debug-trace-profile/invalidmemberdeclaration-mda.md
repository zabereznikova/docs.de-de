---
title: invalidMemberDeclaration-MDA
description: Überprüfen Sie den Assistenten für das Debuggen von ungültetem Debugging, der aufgerufen wird, wenn ein Fehler-HRESULT an com zurückgegeben wird, ohne die verwaltete Methode aufzurufen.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: c8d6c69fc6eb4f5f690b02809fdc492da675c3b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272552"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="123d4-103">invalidMemberDeclaration-MDA</span><span class="sxs-lookup"><span data-stu-id="123d4-103">invalidMemberDeclaration MDA</span></span>

<span data-ttu-id="123d4-104">Der `invalidMemberDeclaration`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, um einen Fehler zu melden, der aufgetreten ist, als ermittelt werden sollte, wie das Marshalling für die Parameter eines Members zu erfolgen hat, das aus COM aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="123d4-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="123d4-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="123d4-105">Symptoms</span></span>  

 <span data-ttu-id="123d4-106">Es wird ein Fehler-HRESULT an COM zurückgegeben, ohne dass die verwaltete Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="123d4-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="123d4-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="123d4-107">Cause</span></span>  

 <span data-ttu-id="123d4-108">Dies wird höchstwahrscheinlich durch ein inkompatibles <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut für einen der Parameter verursacht.</span><span class="sxs-lookup"><span data-stu-id="123d4-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="123d4-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="123d4-109">Resolution</span></span>  

 <span data-ttu-id="123d4-110">Geben Sie gültige <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribute für die Parameter an.</span><span class="sxs-lookup"><span data-stu-id="123d4-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="123d4-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="123d4-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="123d4-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="123d4-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="123d4-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="123d4-113">Output</span></span>  

 <span data-ttu-id="123d4-114">Eine Informationsmeldung, die den Membernamen, den Typnamen und die Fehlermeldung enthält.</span><span class="sxs-lookup"><span data-stu-id="123d4-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="123d4-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="123d4-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="123d4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="123d4-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="123d4-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="123d4-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="123d4-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="123d4-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
