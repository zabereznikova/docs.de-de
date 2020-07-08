---
title: memberInfoCacheCreation-MDA
description: Informieren Sie sich über den Mitgliedschaften für den Assistenten für verwaltetes Debuggen (MDA) in .net, der aktiviert wird, wenn ein Mitgliedschaften-Cache erstellt wird.
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
ms.openlocfilehash: c48be7ac8632b8072981be01e01997ee8c34b6b3
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051141"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="4ab03-103">memberInfoCacheCreation-MDA</span><span class="sxs-lookup"><span data-stu-id="4ab03-103">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="4ab03-104">Der `memberInfoCacheCreation`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein <xref:System.Reflection.MemberInfo>-Cache erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4ab03-104">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="4ab03-105">Dies ist ein starkes Anzeichen für ein Programm, das ressourcenintensive Reflektionsfunktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ab03-105">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4ab03-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="4ab03-106">Symptoms</span></span>  
 <span data-ttu-id="4ab03-107">Der Arbeitssatz eines Programms wird vergrößert, weil das Programm ressourcenintensive Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ab03-107">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4ab03-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="4ab03-108">Cause</span></span>  
 <span data-ttu-id="4ab03-109">Reflektionsvorgänge, bei denen <xref:System.Reflection.MemberInfo>-Objekte einbezogen werden, gelten als ressourcenintensiv, da sie Metadaten lesen müssen, die in kalten Seiten gespeichert sind und angeben, dass das Programm irgendeine Form von spät gebundenen Szenarios verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ab03-109">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4ab03-110">Lösung</span><span class="sxs-lookup"><span data-stu-id="4ab03-110">Resolution</span></span>  
 <span data-ttu-id="4ab03-111">Sie können feststellen, wann Reflektion in Ihrem Programm verwendet wird, indem Sie diesen MDA aktivieren und den Code dann in einem Debugger ausführen oder mit einem Debugger anfügen, wenn der MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4ab03-111">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="4ab03-112">Mit einem Debugger erhalten Sie eine Stapelüberwachung, die zeigt, wo der <xref:System.Reflection.MemberInfo>-Cache erstellt wurde. Von dort aus können Sie feststellen, wann Ihr Programm Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ab03-112">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="4ab03-113">Die Lösung ist abhängig von den Zielen des Codes.</span><span class="sxs-lookup"><span data-stu-id="4ab03-113">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="4ab03-114">Dieser MDA weist Sie darauf hin, dass das Programm ein spät gebundenes Szenario aufweist.</span><span class="sxs-lookup"><span data-stu-id="4ab03-114">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="4ab03-115">Möglicherweise möchten Sie bestimmen, ob Sie ein früh gebundenes Szenario ersetzen oder die Leistung des spät gebundenen Szenarios berücksichtigen können.</span><span class="sxs-lookup"><span data-stu-id="4ab03-115">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4ab03-116">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4ab03-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="4ab03-117">Dieser MDA wird für jeden <xref:System.Reflection.MemberInfo>-Cache aktiviert, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4ab03-117">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="4ab03-118">Die Auswirkungen auf die Leistung sind geringfügig.</span><span class="sxs-lookup"><span data-stu-id="4ab03-118">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4ab03-119">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="4ab03-119">Output</span></span>  
 <span data-ttu-id="4ab03-120">Der MDA gibt eine Meldung aus, die anzeigt, dass der <xref:System.Reflection.MemberInfo>-Cache erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4ab03-120">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="4ab03-121">Verwenden Sie einen Debugger, um eine Stapelüberwachung zu erhalten, die anzeigt, wann Ihr Programm Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ab03-121">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4ab03-122">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4ab03-122">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="4ab03-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ab03-123">Example</span></span>  
 <span data-ttu-id="4ab03-124">Dieser Beispielcode aktiviert den `memberInfoCacheCreation`-MDA.</span><span class="sxs-lookup"><span data-stu-id="4ab03-124">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ab03-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ab03-125">See also</span></span>

- <xref:System.Reflection.MemberInfo>
- [<span data-ttu-id="4ab03-126">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="4ab03-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
