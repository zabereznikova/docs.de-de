---
title: memberInfoCacheCreation-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ebc449985a8e2617b278f04c91d243ca11b637e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145201"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="f82ab-102">memberInfoCacheCreation-MDA</span><span class="sxs-lookup"><span data-stu-id="f82ab-102">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="f82ab-103">Der `memberInfoCacheCreation`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein <xref:System.Reflection.MemberInfo>-Cache erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f82ab-103">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="f82ab-104">Dies ist ein starkes Anzeichen für ein Programm, das ressourcenintensive Reflektionsfunktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f82ab-104">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f82ab-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="f82ab-105">Symptoms</span></span>  
 <span data-ttu-id="f82ab-106">Der Arbeitssatz eines Programms wird vergrößert, weil das Programm ressourcenintensive Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="f82ab-106">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f82ab-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="f82ab-107">Cause</span></span>  
 <span data-ttu-id="f82ab-108">Reflektionsvorgänge, bei denen <xref:System.Reflection.MemberInfo>-Objekte einbezogen werden, gelten als ressourcenintensiv, da sie Metadaten lesen müssen, die in kalten Seiten gespeichert sind und angeben, dass das Programm irgendeine Form von spät gebundenen Szenarios verwendet.</span><span class="sxs-lookup"><span data-stu-id="f82ab-108">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f82ab-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="f82ab-109">Resolution</span></span>  
 <span data-ttu-id="f82ab-110">Sie können feststellen, wann Reflektion in Ihrem Programm verwendet wird, indem Sie diesen MDA aktivieren und den Code dann in einem Debugger ausführen oder mit einem Debugger anfügen, wenn der MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f82ab-110">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="f82ab-111">Mit einem Debugger erhalten Sie eine Stapelüberwachung, die zeigt, wo der <xref:System.Reflection.MemberInfo>-Cache erstellt wurde. Von dort aus können Sie feststellen, wann Ihr Programm Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="f82ab-111">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="f82ab-112">Die Lösung ist abhängig von den Zielen des Codes.</span><span class="sxs-lookup"><span data-stu-id="f82ab-112">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="f82ab-113">Dieser MDA weist Sie darauf hin, dass das Programm ein spät gebundenes Szenario aufweist.</span><span class="sxs-lookup"><span data-stu-id="f82ab-113">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="f82ab-114">Möglicherweise möchten Sie bestimmen, ob Sie ein früh gebundenes Szenario ersetzen oder die Leistung des spät gebundenen Szenarios berücksichtigen können.</span><span class="sxs-lookup"><span data-stu-id="f82ab-114">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f82ab-115">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f82ab-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="f82ab-116">Dieser MDA wird für jeden <xref:System.Reflection.MemberInfo>-Cache aktiviert, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f82ab-116">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="f82ab-117">Die Auswirkungen auf die Leistung sind geringfügig.</span><span class="sxs-lookup"><span data-stu-id="f82ab-117">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f82ab-118">Output</span><span class="sxs-lookup"><span data-stu-id="f82ab-118">Output</span></span>  
 <span data-ttu-id="f82ab-119">Der MDA gibt eine Meldung aus, die anzeigt, dass der <xref:System.Reflection.MemberInfo>-Cache erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f82ab-119">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="f82ab-120">Verwenden Sie einen Debugger, um eine Stapelüberwachung zu erhalten, die anzeigt, wann Ihr Programm Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="f82ab-120">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f82ab-121">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f82ab-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="f82ab-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f82ab-122">Example</span></span>  
 <span data-ttu-id="f82ab-123">Dieser Beispielcode aktiviert den `memberInfoCacheCreation`-MDA.</span><span class="sxs-lookup"><span data-stu-id="f82ab-123">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f82ab-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f82ab-124">See Also</span></span>  
 <xref:System.Reflection.MemberInfo>  
 [<span data-ttu-id="f82ab-125">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="f82ab-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
