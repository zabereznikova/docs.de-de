---
title: loadFromContext-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: d0090a0272d1c3b6175b351175689df1e1e4fdbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181807"
---
# <a name="loadfromcontext-mda"></a><span data-ttu-id="bc6e9-102">loadFromContext-MDA</span><span class="sxs-lookup"><span data-stu-id="bc6e9-102">loadFromContext MDA</span></span>
<span data-ttu-id="bc6e9-103">Der `loadFromContext`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Assembly in den `LoadFrom`-Kontext geladen wird.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-103">The `loadFromContext` managed debugging assistant (MDA) is activated if an assembly is loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="bc6e9-104">Diese Situation kann als Ergebnis eines <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Aufrufs oder anderer ähnlichen Methoden auftreten.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-104">This situation can occur as a result of calling <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or other similar methods.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bc6e9-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="bc6e9-105">Symptoms</span></span>  
 <span data-ttu-id="bc6e9-106">Das Verwenden einiger Ladeprogrammmethoden kann dazu führen, dass Assemblys im `LoadFrom`-Kontext geladen werden.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-106">The use of some loader methods can result in assemblies being loaded in the `LoadFrom` context.</span></span> <span data-ttu-id="bc6e9-107">Das Verwenden dieses Kontexts kann zu unerwartetem Verhalten für die Serialisierung, Umwandlung und Lösung von Abhängigkeiten führen.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-107">The use of this context can result in unexpected behavior for serialization, casting, and dependency resolution.</span></span> <span data-ttu-id="bc6e9-108">Im Allgemeinen wird empfohlen, dass Assemblys im `Load`-Kontext geladen werden, um diese Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-108">In general, it is recommended that assemblies be loaded into the `Load` context to avoid these problems.</span></span> <span data-ttu-id="bc6e9-109">Es ist schwierig, ohne diesen MDA zu ermitteln, in welchem Kontext eine Assembly geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-109">It is difficult to determine which context an assembly has been loaded into without this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bc6e9-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="bc6e9-110">Cause</span></span>  
 <span data-ttu-id="bc6e9-111">Im Allgemeinen wurde eine Assembly in den `LoadFrom`-Kontext geladen, wenn sie aus einem Pfad außerhalb des `Load`-Kontexts geladen wurde, z.B. im globalen Assemblycache oder in der <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-111">Generally, an assembly was loaded into the `LoadFrom` context if it was loaded from a path outside the `Load` context, such as the global assembly cache or the <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bc6e9-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="bc6e9-112">Resolution</span></span>  
 <span data-ttu-id="bc6e9-113">Konfigurieren Sie Anwendungen so, dass <xref:System.Reflection.Assembly.LoadFrom%2A>-Aufrufe nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-113">Configure applications such that <xref:System.Reflection.Assembly.LoadFrom%2A> calls are no longer needed.</span></span> <span data-ttu-id="bc6e9-114">Hierfür können Sie die folgenden Verfahren verwenden:</span><span class="sxs-lookup"><span data-stu-id="bc6e9-114">You can use the following techniques for doing so:</span></span>  
  
- <span data-ttu-id="bc6e9-115">Installieren Sie Assemblys im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-115">Install assemblies in the global assembly cache.</span></span>  
  
- <span data-ttu-id="bc6e9-116">Platzieren Sie Assemblys in das <xref:System.AppDomainSetup.ApplicationBase%2A>-Verzeichnis für die <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-116">Place assemblies in the <xref:System.AppDomainSetup.ApplicationBase%2A> directory for the <xref:System.AppDomain>.</span></span> <span data-ttu-id="bc6e9-117">Im Fall der Standarddomäne enthält das <xref:System.AppDomainSetup.ApplicationBase%2A>-Verzeichnis die ausführbare Datei, die den Prozess gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-117">In the case of the default domain, the <xref:System.AppDomainSetup.ApplicationBase%2A> directory is the one that contains the executable file that started the process.</span></span> <span data-ttu-id="bc6e9-118">Dies erfordert möglicherweise auch das Erstellen eines neuen <xref:System.AppDomain>, wenn es nicht möglich ist, die Assembly zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-118">This might also require creating a new <xref:System.AppDomain> if it is not convenient to move the assembly.</span></span>  
  
- <span data-ttu-id="bc6e9-119">Fügen Sie einen Überprüfungspfad zu Ihrer Anwendungskonfigurationsdatei (.config) oder zu sekundären Anwendungsdomänen hinzu, wenn abhängige Assemblys in untergeordneten Verzeichnissen relativ zur ausführbaren Datei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-119">Add a probing path to your application configuration (.config) file or to secondary  application domains if dependent assemblies are in child directories relative to the executable.</span></span>  
  
 <span data-ttu-id="bc6e9-120">In jedem Fall kann der Code geändert werden, um die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-120">In each case, the code can be changed to use the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bc6e9-121">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bc6e9-121">Effect on the Runtime</span></span>  
 <span data-ttu-id="bc6e9-122">Der MDA hat keinen Einfluss auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-122">The MDA does not have any effect on the CLR.</span></span> <span data-ttu-id="bc6e9-123">Er gibt den Kontext an, der als Ergebnis einer Ladeanforderung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-123">It reports the context that was used as a result of a load request.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bc6e9-124">Output</span><span class="sxs-lookup"><span data-stu-id="bc6e9-124">Output</span></span>  
 <span data-ttu-id="bc6e9-125">Der MDA meldet, dass die Assembly in den `LoadFrom`-Kontext geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-125">The MDA reports that the assembly was loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="bc6e9-126">Er gibt den einfachen Namen der Assembly und den Pfad an.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-126">It specifies the simple name of the assembly and the path.</span></span> <span data-ttu-id="bc6e9-127">Er weist auch auf Möglichkeiten hin, um das Verwenden des `LoadFrom`-Kontexts zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="bc6e9-127">It also suggests mitigations to avoid using the `LoadFrom` context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bc6e9-128">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bc6e9-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="bc6e9-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc6e9-129">Example</span></span>  
 <span data-ttu-id="bc6e9-130">Im folgenden Codebeispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann:</span><span class="sxs-lookup"><span data-stu-id="bc6e9-130">The following code example demonstrates a situation that can activate this MDA:</span></span>  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is
            // located outside of the Load context probing path.
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc6e9-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc6e9-131">See also</span></span>

- [<span data-ttu-id="bc6e9-132">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="bc6e9-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
