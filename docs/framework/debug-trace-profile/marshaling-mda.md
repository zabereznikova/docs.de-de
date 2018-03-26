---
title: Marshalling-MDA
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
caps.latest.revision: ''
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 83b621f78e3ba4641540f6125ed14d600cc292d1
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="marshaling-mda"></a><span data-ttu-id="c40b4-102">Marshalling-MDA</span><span class="sxs-lookup"><span data-stu-id="c40b4-102">marshaling MDA</span></span>
<span data-ttu-id="c40b4-103">Der `marshaling`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR Marshallinginformationen für einen Methodenparameter oder das Feld einer Struktur einrichtet.</span><span class="sxs-lookup"><span data-stu-id="c40b4-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="c40b4-104">Dieser MDA funktioniert nicht mit JIT-kompilierten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c40b4-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c40b4-105">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c40b4-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="c40b4-106">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="c40b4-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c40b4-107">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="c40b4-107">Output</span></span>  
 <span data-ttu-id="c40b4-108">Der MDA zeigt den Typ des Parameters bzw. Felds in den verwalteten und nicht verwalteten Kontexten sowie die Struktur bzw. Methode an, die diesen Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="c40b4-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="c40b4-109">Das Folgende ist ein Beispiel für die Ausgabe für ein Feld:</span><span class="sxs-lookup"><span data-stu-id="c40b4-109">The following is an example of the output for a field:</span></span>  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="c40b4-110">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c40b4-110">Configuration</span></span>  
 <span data-ttu-id="c40b4-111">Durch Konfigurieren des MDA können Sie die gemeldeten Marshallinginformationen anhand der betroffenen Feld- oder Methodennamen filtern.</span><span class="sxs-lookup"><span data-stu-id="c40b4-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="c40b4-112">Im folgenden Beispiel wird gezeigt, wie die Elemente `methodFilter`, `fieldFilter` und `match` verwendet werden, um Filter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c40b4-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="c40b4-113">Wird das `name`-Attribut auf ein Sternchen (\*) festgelegt, werden alle Namen erfasst.</span><span class="sxs-lookup"><span data-stu-id="c40b4-113">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c40b4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c40b4-114">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="c40b4-115">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="c40b4-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="c40b4-116">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="c40b4-116">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
