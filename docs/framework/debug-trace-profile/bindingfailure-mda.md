---
title: bindingFailure-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding failure
- binding, failures
- MDAs (managed debugging assistants), binding failures
- assemblies [.NET Framework], binding failures
- managed debugging assistants (MDAs), binding failures
- BindingFailure MDA
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 89c1ce4b39379aeae80240750cdbcd2e61b6ec11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="bindingfailure-mda"></a><span data-ttu-id="f53a5-102">bindingFailure-MDA</span><span class="sxs-lookup"><span data-stu-id="f53a5-102">bindingFailure MDA</span></span>
<span data-ttu-id="f53a5-103">Der `bindingFailure`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn das Laden einer Assembly fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="f53a5-103">The `bindingFailure` managed debugging assistant (MDA) is activated when an assembly fails to load.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f53a5-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="f53a5-104">Symptoms</span></span>  
 <span data-ttu-id="f53a5-105">Es wurde versucht, eine Assembly mithilfe eines statischen Verweises oder einer der Ladeprogrammmethoden wie <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> zu laden.</span><span class="sxs-lookup"><span data-stu-id="f53a5-105">Code has attempted to load an assembly using a static reference or one of the loader methods, such as <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f53a5-106">Die Assembly wird nicht geladen, und es wird eine <xref:System.IO.FileNotFoundException>- bzw. <xref:System.IO.FileLoadException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f53a5-106">The assembly is not loaded and a <xref:System.IO.FileNotFoundException> or <xref:System.IO.FileLoadException> exception is thrown.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f53a5-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="f53a5-107">Cause</span></span>  
 <span data-ttu-id="f53a5-108">Ein Bindungsfehler tritt auf, wenn eine Assembly nicht durch die Common Language Runtime geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f53a5-108">A binding failure occurs when the runtime is unable to load an assembly.</span></span> <span data-ttu-id="f53a5-109">Ein Bindungsfehler kann das Ergebnis einer der folgenden Situationen sein:</span><span class="sxs-lookup"><span data-stu-id="f53a5-109">A binding failure might be the result of one of the following situations:</span></span>  
  
-   <span data-ttu-id="f53a5-110">Die Common Language Runtime (CLR) kann die angeforderte Assembly nicht finden.</span><span class="sxs-lookup"><span data-stu-id="f53a5-110">The common language runtime (CLR) cannot find the requested assembly.</span></span> <span data-ttu-id="f53a5-111">Es gibt viele Ursachen dafür. Beispielsweise ist die Assembly nicht installiert, oder die Anwendung wurde nicht ordnungsgemäß zum Finden der Assembly konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f53a5-111">There are many reasons this can occur, such as the assembly not being installed or the application not being correctly configured to find the assembly.</span></span>  
  
-   <span data-ttu-id="f53a5-112">Häufig treten Probleme beim Übergeben eines Typs an eine andere Anwendungsdomäne auf. Dazu muss die CLR die Assembly mit diesem Typ in die andere Anwendungsdomäne laden.</span><span class="sxs-lookup"><span data-stu-id="f53a5-112">A common problem scenario is passing a type to another application domain, which requires the CLR to load the assembly containing that type in the other application domain.</span></span> <span data-ttu-id="f53a5-113">Wenn die andere Anwendungsdomäne anders konfiguriert ist als die ursprüngliche Anwendungsdomäne, kann die CLR die Assembly unter Umständen nicht laden.</span><span class="sxs-lookup"><span data-stu-id="f53a5-113">It may not be possible for the runtime to load the assembly if the other application domain is configured differently from the original application domain.</span></span> <span data-ttu-id="f53a5-114">Zum Beispiel verfügen die beiden Anwendungsdomänen möglicherweise über unterschiedliche <xref:System.AppDomain.BaseDirectory%2A>-Eigenschaftswerte.</span><span class="sxs-lookup"><span data-stu-id="f53a5-114">For example, the two application domains might have different <xref:System.AppDomain.BaseDirectory%2A> property values.</span></span>  
  
-   <span data-ttu-id="f53a5-115">Die angeforderte Assembly ist beschädigt, oder es handelt sich nicht um eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="f53a5-115">The requested assembly is corrupted or is not an assembly.</span></span>  
  
-   <span data-ttu-id="f53a5-116">Der Programmcode, der die Assembly zu laden versucht, verfügt nicht über die richtigen Sicherheitsberechtigungen für den Codezugriff zum Laden von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f53a5-116">The code attempting to load the assembly does not have the correct code access security permissions to load assemblies.</span></span>  
  
-   <span data-ttu-id="f53a5-117">Den Benutzeranmeldeinformationen sind nicht die erforderlichen Berechtigungen zum Lesen der Datei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f53a5-117">The user credentials do not provide the required permissions to read the file.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f53a5-118">Auflösung</span><span class="sxs-lookup"><span data-stu-id="f53a5-118">Resolution</span></span>  
 <span data-ttu-id="f53a5-119">Der erste Schritt ist zu ermitteln, warum die CLR keine Bindung der angeforderten Assembly durchführen konnte.</span><span class="sxs-lookup"><span data-stu-id="f53a5-119">The first step is to determine why the CLR could not bind to the requested assembly.</span></span> <span data-ttu-id="f53a5-120">Es gibt viele Ursachen, warum die CLR die angeforderte Assembly nicht gefunden hat bzw. nicht laden konnte (siehe die im Abschnitt „Ursache“ aufgeführten Szenarios).</span><span class="sxs-lookup"><span data-stu-id="f53a5-120">There are many reasons why the runtime might not have found or been able load the requested assembly, such as the scenarios listed in the Cause section.</span></span> <span data-ttu-id="f53a5-121">Die folgenden Aktionen werden empfohlen, um die Ursache des Bindungsfehlers zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="f53a5-121">The following actions are recommended to eliminate the cause of the binding failure:</span></span>  
  
-   <span data-ttu-id="f53a5-122">Bestimmen Sie die Ursache, indem Sie die vom `bindingFailure`-MDA bereitgestellten Daten auswerten:</span><span class="sxs-lookup"><span data-stu-id="f53a5-122">Determine the cause by using the data provided by the `bindingFailure` MDA:</span></span>  
  
    -   <span data-ttu-id="f53a5-123">Starten Sie [Fuslogvw.exe (Assembly Binding Log Viewer)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md), um die bei der Assemblybindung erzeugten Fehlerprotokolle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f53a5-123">Run the [Fuslogvw.exe (Assembly Binding Log Viewer)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md) to read the error logs produced by the assembly binder.</span></span>  
  
    -   <span data-ttu-id="f53a5-124">Stellen Sie fest, ob sich die Assembly am angegebenen Speicherort befindet.</span><span class="sxs-lookup"><span data-stu-id="f53a5-124">Determine if the assembly is at the location requested.</span></span> <span data-ttu-id="f53a5-125">Im Fall der <xref:System.Reflection.Assembly.LoadFrom%2A>- und <xref:System.Reflection.Assembly.LoadFile%2A>-Methoden kann der angeforderte Speicherort leicht ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f53a5-125">In the case of the <xref:System.Reflection.Assembly.LoadFrom%2A> and <xref:System.Reflection.Assembly.LoadFile%2A> methods, the requested location can be easily determined.</span></span> <span data-ttu-id="f53a5-126">Im Fall der <xref:System.Reflection.Assembly.Load%2A>-Methode, bei der die Bindung mithilfe der Assemblyidentität erfolgt, müssen Sie nach Assemblys mit dieser Identität in der Überprüfungspfadeigenschaft <xref:System.AppDomain.BaseDirectory%2A> der Anwendungsdomäne und im globalen Assemblycache suchen.</span><span class="sxs-lookup"><span data-stu-id="f53a5-126">In the case of the <xref:System.Reflection.Assembly.Load%2A> method, which binds using the assembly identity, you must look for assemblies that match that identity in the application domain's <xref:System.AppDomain.BaseDirectory%2A> property probe path and the global assembly cache.</span></span>  
  
-   <span data-ttu-id="f53a5-127">Beheben Sie die Fehlerursache in Abhängigkeit vom Ergebnis der Ursachensuche.</span><span class="sxs-lookup"><span data-stu-id="f53a5-127">Resolve the cause based on the preceding determination.</span></span> <span data-ttu-id="f53a5-128">Mögliche Vorgehensweisen zum Lösen des Problems:</span><span class="sxs-lookup"><span data-stu-id="f53a5-128">Possible resolution options are the following:</span></span>  
  
    -   <span data-ttu-id="f53a5-129">Installieren Sie die angeforderte Assembly im globalen Assemblycache, und rufen Sie die</span><span class="sxs-lookup"><span data-stu-id="f53a5-129">Install the requested assembly in the global assembly cache and call the.</span></span> <span data-ttu-id="f53a5-130"><xref:System.Reflection.Assembly.Load%2A>-Methode, um die Assembly nach Identität zu laden.</span><span class="sxs-lookup"><span data-stu-id="f53a5-130"><xref:System.Reflection.Assembly.Load%2A> method to load the assembly by identity.</span></span>  
  
    -   <span data-ttu-id="f53a5-131">Kopieren Sie die angeforderte Assembly in das Anwendungsverzeichnis, und rufen Sie die <xref:System.Reflection.Assembly.Load%2A>-Methode auf, um die Assembly nach Identität zu laden.</span><span class="sxs-lookup"><span data-stu-id="f53a5-131">Copy the requested assembly into the application directory and call the <xref:System.Reflection.Assembly.Load%2A> method to load the assembly by identity.</span></span>  
  
    -   <span data-ttu-id="f53a5-132">Konfigurieren Sie die Anwendungsdomäne mit dem Bindungsfehler so um, dass sie den Pfad zur Assembly enthält. Ändern Sie dazu entweder die <xref:System.AppDomain.BaseDirectory%2A>-Eigenschaft, oder fügen Sie private Überprüfungspfade hinzu.</span><span class="sxs-lookup"><span data-stu-id="f53a5-132">Reconfigure the application domain in which the binding failure occurred to include the assembly path by either changing the <xref:System.AppDomain.BaseDirectory%2A> property or adding private probing paths.</span></span>  
  
    -   <span data-ttu-id="f53a5-133">Ändern Sie die Zugriffssteuerungsliste der Datei, damit diese vom angemeldeten Benutzer gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f53a5-133">Change the access control list for the file to allow the logged-on user to read the file.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f53a5-134">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f53a5-134">Effect on the Runtime</span></span>  
 <span data-ttu-id="f53a5-135">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="f53a5-135">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="f53a5-136">Es werden nur Daten über Bindungsfehler bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f53a5-136">It only reports data about binding failures.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f53a5-137">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="f53a5-137">Output</span></span>  
 <span data-ttu-id="f53a5-138">Der MDA meldet die Assembly, die nicht geladen wurde, den angeforderten Pfad und/oder den Anzeigenamen, den Bindungskontext, die Anwendungsdomäne für den angeforderten Ladevorgang und die Fehlerursache.</span><span class="sxs-lookup"><span data-stu-id="f53a5-138">The MDA reports the assembly that failed to load, including the requested path and/or display name, the binding context, the application domain in which the load was requested, and the reason for the failure.</span></span>  
  
 <span data-ttu-id="f53a5-139">Die Angaben zu Anzeigename oder angefordertem Pfad sind möglicherweise leer, wenn diese Daten der CLR nicht zur Verfügung standen.</span><span class="sxs-lookup"><span data-stu-id="f53a5-139">The display name or requested path may be blank if that data was not available to the CLR.</span></span> <span data-ttu-id="f53a5-140">Wenn der fehlgeschlagene Aufruf ein Aufruf der <xref:System.Reflection.Assembly.Load%2A>-Methode war, konnte die CLR wahrscheinlich den Anzeigenamen der Assembly nicht ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f53a5-140">If the call that failed was to the <xref:System.Reflection.Assembly.Load%2A> method, it is likely the runtime could not determine the display name for the assembly.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f53a5-141">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f53a5-141">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <bindingFailure />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="f53a5-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f53a5-142">Example</span></span>  
 <span data-ttu-id="f53a5-143">Im folgenden Codebeispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann:</span><span class="sxs-lookup"><span data-stu-id="f53a5-143">The following code example demonstrates a situation that can activate this MDA:</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // This call attempts to load a nonexistent assembly.  
            // The call will throw a System.IO.FileNotFound exception  
            // and cause the activation of the bindingFailure MDA   
            // if it is registered.  
            Assembly.Load("NonExistentAssembly");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f53a5-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f53a5-144">See Also</span></span>  
 [<span data-ttu-id="f53a5-145">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="f53a5-145">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
