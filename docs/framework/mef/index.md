---
title: Managed Extensibility Framework (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 323dfe7d68f5a6f6274ce23f82e25a337956b23c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43386427"
---
# <a name="managed-extensibility-framework-mef"></a><span data-ttu-id="2be9a-102">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="2be9a-102">Managed Extensibility Framework (MEF)</span></span>
<span data-ttu-id="2be9a-103">Dieses Thema bietet eine Übersicht über das in .NET Framework 4 eingeführte Managed Extensibility Framework.</span><span class="sxs-lookup"><span data-stu-id="2be9a-103">This topic provides an overview of the Managed Extensibility Framework introduced in the .NET Framework 4.</span></span>  
  
<a name="what_is_mef"></a>   
## <a name="what-is-mef"></a><span data-ttu-id="2be9a-104">Was ist MEF?</span><span class="sxs-lookup"><span data-stu-id="2be9a-104">What is MEF?</span></span>  
 <span data-ttu-id="2be9a-105">Das Managed Extensibility Framework oder MEF ist eine Bibliothek zum Erstellen von einfachen und erweiterbaren Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-105">The Managed Extensibility Framework or MEF is a library for creating lightweight, extensible applications.</span></span> <span data-ttu-id="2be9a-106">Es ermöglicht Anwendungsentwicklern, Erweiterungen ohne Konfiguration zu ermitteln und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-106">It allows application developers to discover and use extensions with no configuration required.</span></span> <span data-ttu-id="2be9a-107">Das Framework ermöglicht Erweiterungsentwicklern, Code leicht zu kapseln und zerbrechliche harte Abhängigkeiten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-107">It also lets extension developers easily encapsulate code and avoid fragile hard dependencies.</span></span> <span data-ttu-id="2be9a-108">MEF ermöglicht nicht nur die Wiederverwendung von Erweiterungen innerhalb von Anwendungen, sondern auch anwendungsübergreifend.</span><span class="sxs-lookup"><span data-stu-id="2be9a-108">MEF not only allows extensions to be reused within applications, but across applications as well.</span></span>  
  
<a name="the_problem_of_extensibility"></a>   
## <a name="the-problem-of-extensibility"></a><span data-ttu-id="2be9a-109">Das Problem der Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="2be9a-109">The Problem of Extensibility</span></span>  
 <span data-ttu-id="2be9a-110">Angenommen, Sie entwickeln eine komplexe erweiterungsfähige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2be9a-110">Imagine that you are the architect of a large application that must provide support for extensibility.</span></span> <span data-ttu-id="2be9a-111">Die Anwendung umfasst eine große Anzahl kleinerer Komponenten und ist gleichzeitig für das Erstellen und Ausführen der Komponenten zuständig.</span><span class="sxs-lookup"><span data-stu-id="2be9a-111">Your application has to include a potentially large number of smaller components, and is responsible for creating and running them.</span></span>  
  
 <span data-ttu-id="2be9a-112">Der einfachste Lösungsansatz ist, die Komponenten als Quellcode in die Anwendung zu integrieren und sie direkt vom Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-112">The simplest approach to the problem is to include the components as source code in your application, and call them directly from your code.</span></span>  <span data-ttu-id="2be9a-113">Hierbei ergeben sich allerdings mehrere offensichtliche Nachteile.</span><span class="sxs-lookup"><span data-stu-id="2be9a-113">This has a number of obvious drawbacks.</span></span>  <span data-ttu-id="2be9a-114">Zunächst einmal können keine neuen Komponenten hinzugefügt werden, ohne dabei den Quellcode zu ändern. Dies wäre zwar für eine Webanwendung, jedoch nicht für eine Clientanwendung akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="2be9a-114">Most importantly, you cannot add new components without modifying the source code, a restriction that might be acceptable in, for example, a Web application, but is unworkable in a client application.</span></span>  <span data-ttu-id="2be9a-115">Außerdem kann möglicherweise nicht auf den Quellcode der Komponenten zugegriffen werden, da diese eventuell von Drittanbietern entwickelt wurden. Aus dem gleichen Grund darf den Komponenten auch nicht der Zugriff auf Ihren Quellcode gestattet werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-115">Equally problematic, you may not have access to the source code for the components, because they might be developed by third parties, and for the same reason you cannot allow them to access yours.</span></span>  
  
 <span data-ttu-id="2be9a-116">Eine elegantere Möglichkeit wäre die Bereitstellung eines Erweiterungspunkts oder einer Schnittstelle, um die Komponenten von der Anwendung zu entkoppeln.</span><span class="sxs-lookup"><span data-stu-id="2be9a-116">A slightly more sophisticated approach would be to provide an extension point or interface, to permit decoupling between the application and its components.</span></span>  <span data-ttu-id="2be9a-117">Bei diesem Modell kann eine Schnittstelle zur Implementierung einer Komponente und eine API zur Interaktion mit der Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-117">Under this model, you might provide an interface that a component can implement, and an API to enable it to interact with your application.</span></span>  <span data-ttu-id="2be9a-118">So ist die Gewährung von Quellcodezugriff nicht mehr erforderlich, allerdings müssen hier andere Schwierigkeiten beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-118">This solves the problem of requiring source code access, but it still has its own difficulties.</span></span>  
  
 <span data-ttu-id="2be9a-119">Da von der Anwendung Komponenten nicht selbständig ermittelt werden können, müssen die verfügbaren und zu ladenden Komponenten exakt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-119">Because the application lacks any capacity for discovering components on its own, it must still be explicitly told which components are available and should be loaded.</span></span>  <span data-ttu-id="2be9a-120">Hierfür werden in der Regel die verfügbaren Komponenten in einer Konfigurationsdatei genau registriert.</span><span class="sxs-lookup"><span data-stu-id="2be9a-120">This is typically accomplished by explicitly registering the available components in a configuration file.</span></span> <span data-ttu-id="2be9a-121">Das Gewährleisten der Verwendung der richtigen Komponenten kann also zu einem Wartungsproblem werden, insbesondere, wenn die Aktualisierung vom Endbenutzer und nicht vom Entwickler durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="2be9a-121">This means that assuring that the components are correct becomes a maintenance issue, particularly if it is the end user and not the developer who is expected to do the updating.</span></span>  
  
 <span data-ttu-id="2be9a-122">Außerdem können Komponenten nicht untereinander kommunizieren, außer durch die fest definierten Channels der Anwendung selbst.</span><span class="sxs-lookup"><span data-stu-id="2be9a-122">In addition, components are incapable of communicating with one another, except through the rigidly defined channels of the application itself.</span></span>  <span data-ttu-id="2be9a-123">Wurde vom Anwendungsentwickler eine bestimmte Kommunikation nicht eingeplant, kann sie normalerweise nicht stattfinden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-123">If the application architect has not anticipated the need for a particular communication, it is usually impossible.</span></span>  
  
 <span data-ttu-id="2be9a-124">Schließlich müssen sich Komponentenentwickler für harte Abhängigkeiten zwischen Assemblys und den implementierten Schnittstellen entscheiden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-124">Finally, the component developers must accept a hard dependency on what assembly contains the interface they implement.</span></span>  <span data-ttu-id="2be9a-125">Dies kann bei der Verwendung einer Komponente in mehr als einer Anwendung und der Erstellung eines Testframeworks für Komponenten Schwierigkeiten bereiten.</span><span class="sxs-lookup"><span data-stu-id="2be9a-125">This makes it difficult for a component to be used in more than one application, and can also create problems when you create a test framework for components.</span></span>  
  
<a name="what_mef_provides"></a>   
## <a name="what-mef-provides"></a><span data-ttu-id="2be9a-126">Dies wird von MEF bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="2be9a-126">What MEF Provides</span></span>  
 <span data-ttu-id="2be9a-127">Mit MEF ist die explizite Registrierung verfügbarer Komponenten nicht mehr erforderlich, da sie mithilfe von *Komposition* implizit ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="2be9a-127">Instead of this explicit registration of available components, MEF provides a way to discover them implicitly, via *composition*.</span></span>  <span data-ttu-id="2be9a-128">Durch eine MEF-Komponente (*Teil*) werden sowohl die Abhängigkeiten (*Importe*) als auch die verfügbaren Funktionen (*Exporte*) deklarativ angegeben.</span><span class="sxs-lookup"><span data-stu-id="2be9a-128">A MEF component, called a *part*, declaratively specifies both its dependencies (known as *imports*) and what capabilities (known as *exports*) it makes available.</span></span> <span data-ttu-id="2be9a-129">Bei der Erstellung eines Teils werden von der MEF-Kompositions-Engine die von anderen Teilen verfügbaren Komponenten für die Importe bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-129">When a part is created, the MEF composition engine satisfies its imports with what is available from other parts.</span></span>  
  
 <span data-ttu-id="2be9a-130">Auf diese Weise können die im vorherigen Abschnitt erläuterten Probleme vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-130">This approach solves the problems discussed in the previous section.</span></span>  <span data-ttu-id="2be9a-131">Da die Funktionen von den MEF-Teilen deklarativ angegeben werden, sind sie zur Laufzeit auffindbar. Eine Anwendung kann Teile also ohne hartcodierte Verweise oder instabile Konfigurationsdateien nutzen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-131">Because MEF parts declaratively specify their capabilities, they are discoverable at runtime, which means an application can make use of parts without either hard-coded references or fragile configuration files.</span></span>  <span data-ttu-id="2be9a-132">Mit dem MEF können Anwendungen Teile anhand von Metadaten ermitteln und untersuchen. Dabei müssen die Teile nicht instanziiert oder ihre Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-132">MEF allows applications to discover and examine parts by their metadata, without instantiating them or even loading their assemblies.</span></span> <span data-ttu-id="2be9a-133">Daher muss nicht genau angegeben werden, wann und auf welche Weise Erweiterungen geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-133">As a result, there is no need to carefully specify when and how extensions should be loaded.</span></span>  
  
 <span data-ttu-id="2be9a-134">Zusätzlich zu den bereitgestellten Exporten können von einem Teil seine Importe angegeben werden, die von anderen Teilen ausgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-134">In addition to its provided exports, a part can specify its imports, which will be filled by other parts.</span></span>  <span data-ttu-id="2be9a-135">Dies ermöglicht die einfache Kommunikation zwischen Teilen und die optimale Verarbeitung von Code.</span><span class="sxs-lookup"><span data-stu-id="2be9a-135">This makes communication among parts not only possible, but easy, and allows for good factoring of code.</span></span> <span data-ttu-id="2be9a-136">Gemeinsame Dienste von Komponenten können z. B. separat aufgeteilt und leicht geändert oder ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-136">For example, services common to many components can be factored into a separate part and easily modified or replaced.</span></span>  
  
 <span data-ttu-id="2be9a-137">Da im MEF-Modell keine harten Abhängigkeiten für Anwendungsassemblys erforderlich sind, können Erweiterungen in mehreren Anwendungen wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-137">Because the MEF model requires no hard dependency on a particular application assembly, it allows extensions to be reused from application to application.</span></span>  <span data-ttu-id="2be9a-138">So können anwendungsunabhängig auch mühelos Testumgebungen für Erweiterungskomponenten entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-138">This also makes it easy to develop a test harness, independent of the application, to test extension components.</span></span>  
  
 <span data-ttu-id="2be9a-139">Eine erweiterbare, mithilfe des MEF erstellte Anwendung deklariert einen Import, der von Erweiterungskomponenten ausgefüllt werden kann und kann ebenfalls Exporte deklarieren, um Anwendungsdienste für Erweiterungen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-139">An extensible application written by using MEF declares an import that can be filled by extension components, and may also declare exports in order to expose application services to extensions.</span></span>  <span data-ttu-id="2be9a-140">Von jeder Erweiterungskomponente wird ein Export deklariert. Importe können ebenfalls deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-140">Each extension component declares an export, and may also declare imports.</span></span>  <span data-ttu-id="2be9a-141">Auf diese Weise sind Erweiterungskomponenten selbst automatisch erweiterbar.</span><span class="sxs-lookup"><span data-stu-id="2be9a-141">In this way, extension components themselves are automatically extensible.</span></span>  
  
<a name="where_is_mef_available"></a>   
## <a name="where-is-mef-available"></a><span data-ttu-id="2be9a-142">Wo ist MEF verfügbar?</span><span class="sxs-lookup"><span data-stu-id="2be9a-142">Where Is MEF Available?</span></span>  
 <span data-ttu-id="2be9a-143">MEF ist ein wesentlicher Bestandteil des [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] und ist überall dort verfügbar, wo .NET Framework verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2be9a-143">MEF is an integral part of the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], and is available wherever the .NET Framework is used.</span></span>  <span data-ttu-id="2be9a-144">Sie können MEF in Clientanwendungen verwenden, egal ob bei diesen Windows Forms, WPF oder eine andere Technologie zum Einsatz kommt, oder in Serveranwendungen, die ASP.NET verwenden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-144">You can use MEF in your client applications, whether they use Windows Forms, WPF, or any other technology, or in server applications that use ASP.NET.</span></span>  
  
<a name="mef_and_maf"></a>   
## <a name="mef-and-maf"></a><span data-ttu-id="2be9a-145">MEF und MAF</span><span class="sxs-lookup"><span data-stu-id="2be9a-145">MEF and MAF</span></span>  
 <span data-ttu-id="2be9a-146">In früheren Versionen von .NET Framework wurde das Managed Add-in Framework (MAF) eingeführt, das für die Isolation und Verwaltung von Erweiterungen innerhalb von Anwendungen entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="2be9a-146">Previous versions of the .NET Framework introduced the Managed Add-in Framework (MAF), designed to allow applications to isolate and manage extensions.</span></span>  <span data-ttu-id="2be9a-147">Bei MAF befindet sich der Fokus auf einer etwas höheren Ebene als bei MEF und liegt auf der Erweiterungsisolation und dem Laden und Entladen von Assemblys, während bei MEF der Fokus auf Erkennbarkeit, Erweiterbarkeit und Portabilität gerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="2be9a-147">The focus of MAF is slightly higher-level than MEF, concentrating on extension isolation and assembly loading and unloading, while MEF's focus is on discoverability, extensibility, and portability.</span></span>  <span data-ttu-id="2be9a-148">Die zwei Frameworks arbeiten optimal zusammen, und beide können von Einzelanwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-148">The two frameworks interoperate smoothly, and a single application can take advantage of both.</span></span>  
  
<a name="simplecalculator_an_example_application"></a>   
## <a name="simplecalculator-an-example-application"></a><span data-ttu-id="2be9a-149">SimpleCalculator: Eine Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="2be9a-149">SimpleCalculator: An Example Application</span></span>  
 <span data-ttu-id="2be9a-150">Die einfachste Möglichkeit zur Entdeckung der Möglichkeiten von MEF ist das Erstellen einer einfachen MEF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2be9a-150">The simplest way to see what MEF can do is to build a simple MEF application.</span></span> <span data-ttu-id="2be9a-151">In diesem Beispiel erstellen Sie einen einfachen Rechner namens SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="2be9a-151">In this example, you build a very simple calculator named SimpleCalculator.</span></span> <span data-ttu-id="2be9a-152">Das Ziel von SimpleCalculator ist die Erstellung einer Konsolenanwendung, die grundlegende arithmetische Befehle wie "5+3" oder "6-2" verarbeiten kann und korrekte Ergebnisse liefert.</span><span class="sxs-lookup"><span data-stu-id="2be9a-152">The goal of SimpleCalculator is to create a console application that accepts basic arithmetic commands, in the form "5+3" or "6-2", and returns the correct answers.</span></span> <span data-ttu-id="2be9a-153">Mit MEF können mühelos neue Operatoren hinzugefügt werden, ohne dabei den Anwendungscode ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-153">Using MEF, you will be able to add new operators without changing the application code.</span></span>  
  
 <span data-ttu-id="2be9a-154">Der vollständige Code für dieses Beispiel kann unter [SimpleCalculator-Beispiel](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-154">To download the complete code for this example, see the [SimpleCalculator sample](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2be9a-155">Mit SimpleCalculator sollen die Konzepte und die Syntax des MEF veranschaulicht werden. Auf ein realistisches Verwendungsszenario wird in diesem Fall kein Wert gelegt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-155">The purpose of SimpleCalculator is to demonstrate the concepts and syntax of MEF, rather than to necessarily provide a realistic scenario for its use.</span></span> <span data-ttu-id="2be9a-156">Viele der Anwendungen, die am meisten von der Leistungsfähigkeit von MEF profitieren würden, sind komplexer als SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="2be9a-156">Many of the applications that would benefit most from the power of MEF are more complex than SimpleCalculator.</span></span> <span data-ttu-id="2be9a-157">Ausführlichere Beispiele finden Sie unter [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="2be9a-157">For more extensive examples, see the [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) on GitHub.</span></span>
  
 <span data-ttu-id="2be9a-158">Erstellen Sie in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] zunächst ein neues Konsolenanwendungsprojekt mit dem Namen `SimpleCalculator`.</span><span class="sxs-lookup"><span data-stu-id="2be9a-158">To start, in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], create a new Console Application project named `SimpleCalculator`.</span></span> <span data-ttu-id="2be9a-159">Fügen Sie einen Verweis auf die System.ComponentModel.Compositions-Assembly hinzu, in der sich MEF befindet.</span><span class="sxs-lookup"><span data-stu-id="2be9a-159">Add a reference to the System.ComponentModel.Composition assembly, where MEF resides.</span></span> <span data-ttu-id="2be9a-160">Öffnen Sie "Module1.vb" oder "Program.cs", und fügen Sie `Imports`- oder `using`-Anweisungen für System.ComponentModel.Composition und System.ComponentModel.Composition.Hosting hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-160">Open Module1.vb or Program.cs and add `Imports` or `using` statements for System.ComponentModel.Composition and System.ComponentModel.Composition.Hosting.</span></span> <span data-ttu-id="2be9a-161">Diese zwei Namespaces enthalten MEF-Typen, die zur Entwicklung einer erweiterbaren Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2be9a-161">These two namespaces contain MEF types you will need to develop an extensible application.</span></span> <span data-ttu-id="2be9a-162">Fügen Sie in Visual Basic das `Public`-Schlüsselwort der Zeile hinzu, die das `Module1`-Modul deklariert.</span><span class="sxs-lookup"><span data-stu-id="2be9a-162">In Visual Basic, add the `Public` keyword to the line that declares the `Module1` module.</span></span>  
  
<a name="composition_container_and_catalogs"></a>   
## <a name="composition-container-and-catalogs"></a><span data-ttu-id="2be9a-163">Kompositionscontainer und Kataloge</span><span class="sxs-lookup"><span data-stu-id="2be9a-163">Composition Container and Catalogs</span></span>  
 <span data-ttu-id="2be9a-164">Der Kern des MEF-Kompositionsmodells ist der *Kompositionscontainer*, der alle verfügbaren Teile enthält und die Komposition ausführt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-164">The core of the MEF composition model is the *composition container*, which contains all the parts available and performs composition.</span></span>  <span data-ttu-id="2be9a-165">(Mit Komposition ist das Zuweisen von Importen zu Exporten gemeint.)  Der gängigste Kompositionscontainertyp ist <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, den wir auch für SimpleCalculator verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-165">(That is, the matching up of imports to exports.)  The most common type of composition container is <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, and you will use this for SimpleCalculator.</span></span>  
  
 <span data-ttu-id="2be9a-166">Fügen Sie in Visual Basic in der Datei Module1.vb die öffentliche Klasse `Program` hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-166">In Visual Basic, in Module1.vb, add a public class named `Program`.</span></span> <span data-ttu-id="2be9a-167">Fügen Sie anschließend der `Program`-Klasse in "Module1.vb" bzw. "Program.cs" die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-167">Then add the following line to the `Program` class in Module1.vb or Program.cs:</span></span>  
  
```vb  
Dim _container As CompositionContainer  
```  
  
```csharp  
private CompositionContainer _container;  
```  
  
 <span data-ttu-id="2be9a-168">Zur Ermittlung der verfügbaren Teile verwenden Kompositionscontainern einen *Katalog*.</span><span class="sxs-lookup"><span data-stu-id="2be9a-168">In order to discover the parts available to it, the composition containers makes use of a *catalog*.</span></span> <span data-ttu-id="2be9a-169">Ein Katalog ist ein Objekt, durch das ermittelte, aus einer beliebigen Quelle stammende Teile verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-169">A catalog is an object that makes available parts discovered from some source.</span></span>  <span data-ttu-id="2be9a-170">MEF stellt zur Ermittlung von Teilen in bereitgestellten Typen, Assemblys oder Verzeichnissen Kataloge bereit.</span><span class="sxs-lookup"><span data-stu-id="2be9a-170">MEF provides catalogs to discover parts from a provided type, an assembly, or a directory.</span></span> <span data-ttu-id="2be9a-171">Anwendungsentwickler können leicht neue Kataloge zur Ermittlung von Teilen aus anderen Quellen erstellen, z. B. aus einem Webdienst.</span><span class="sxs-lookup"><span data-stu-id="2be9a-171">Application developers can easily create new catalogs to discover parts from other sources, such as a Web service.</span></span>  
  
 <span data-ttu-id="2be9a-172">Fügen Sie der `Program`-Klasse den folgenden Konstruktor hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-172">Add the following constructor to the `Program` class:</span></span>  
  
```vb  
Public Sub New()  
    'An aggregate catalog that combines multiple catalogs  
     Dim catalog = New AggregateCatalog()  
  
    'Adds all the parts found in the same assembly as the Program class  
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))  
  
    'Create the CompositionContainer with the parts in the catalog  
    _container = New CompositionContainer(catalog)  
  
    'Fill the imports of this object  
    Try  
        _container.ComposeParts(Me)  
    Catch ex As Exception  
        Console.WriteLine(ex.ToString)  
    End Try  
End Sub  
```  
  
```csharp  
private Program()  
{  
    //An aggregate catalog that combines multiple catalogs  
    var catalog = new AggregateCatalog();  
    //Adds all the parts found in the same assembly as the Program class  
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));  
  
    //Create the CompositionContainer with the parts in the catalog  
    _container = new CompositionContainer(catalog);  
  
    //Fill the imports of this object  
    try  
    {  
        this._container.ComposeParts(this);  
    }  
    catch (CompositionException compositionException)  
    {  
        Console.WriteLine(compositionException.ToString());  
   }  
}  
```  
  
 <span data-ttu-id="2be9a-173">Durch den Aufruf von <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> wird der Kompositionscontainer angewiesen, einen bestimmten Satz von Teilen zu verfassen (in diesem Fall die aktuelle Instanz von `Program`).</span><span class="sxs-lookup"><span data-stu-id="2be9a-173">The call to <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> tells the composition container to compose a specific set of parts, in this case the current instance of `Program`.</span></span> <span data-ttu-id="2be9a-174">Zu diesem Zeitpunkt wird jedoch keine Aktion ausgeführt, da `Program` über keine Importe zum Füllen verfügt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-174">At this point, however, nothing will happen, since `Program` has no imports to fill.</span></span>  
  
<a name="imports_and_exports_with_attributes"></a>   
## <a name="imports-and-exports-with-attributes"></a><span data-ttu-id="2be9a-175">Importe und Exporte mit Attributen</span><span class="sxs-lookup"><span data-stu-id="2be9a-175">Imports and Exports with Attributes</span></span>  
 <span data-ttu-id="2be9a-176">Importieren Sie zunächst mithilfe von `Program` einen Rechner.</span><span class="sxs-lookup"><span data-stu-id="2be9a-176">First, you have `Program` import a calculator.</span></span> <span data-ttu-id="2be9a-177">Dies ermöglicht die Trennung von Benutzeroberflächenkomponenten, z. B. der Konsolenein- und -ausgabe, die an `Program` geleitet werden, von der Logik des Rechners.</span><span class="sxs-lookup"><span data-stu-id="2be9a-177">This allows the separation of user interface concerns, such as the console input and output that will go into `Program`, from the logic of the calculator.</span></span>  
  
 <span data-ttu-id="2be9a-178">Fügen Sie der `Program` -Klasse folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-178">Add the following code to the `Program` class:</span></span>  
  
```vb  
<Import(GetType(ICalculator))>  
Public Property calculator As ICalculator  
```  
  
```csharp  
[Import(typeof(ICalculator))]  
public ICalculator calculator;  
```  
  
 <span data-ttu-id="2be9a-179">Beachten Sie, dass die Deklaration des `calculator`-Objekts nicht ungewöhnlich ist, aber durch das <xref:System.ComponentModel.Composition.ImportAttribute>-Attribut ergänzt wird.</span><span class="sxs-lookup"><span data-stu-id="2be9a-179">Notice that the declaration of the `calculator` object is not unusual, but that it is decorated with the <xref:System.ComponentModel.Composition.ImportAttribute> attribute.</span></span>  <span data-ttu-id="2be9a-180">Durch das Attribut wird ein Import deklariert, d. h., bei der Komposition des Objekts wird es von der Kompositions-Engine ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-180">This attribute declares something to be an import; that is, it will be filled by the composition engine when the object is composed.</span></span>  
  
 <span data-ttu-id="2be9a-181">Jeder Import weist einen *Vertrag* auf, der bestimmt, welche Exporte dem Import zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="2be9a-181">Every import has a *contract*, which determines what exports it will be matched with.</span></span> <span data-ttu-id="2be9a-182">Der Vertrag kann eine explizit angegebene Zeichenfolge sein oder von MEF aus einem angegebenen Typ, in diesem Fall die `ICalculator`-Schnittstelle, automatisch generiert werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-182">The contract can be an explicitly specified string, or it can be automatically generated by MEF from a given type, in this case the interface `ICalculator`.</span></span>  <span data-ttu-id="2be9a-183">Jeder mit einem entsprechenden Vertrag deklarierte Export kann diesem Import zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-183">Any export declared with a matching contract will fulfill this import.</span></span>  <span data-ttu-id="2be9a-184">Der Typ des `calculator`-Objekts ist zwar tatsächlich `ICalculator`, allerdings ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2be9a-184">Note that while the type of the `calculator` object is in fact `ICalculator`, this is not required.</span></span> <span data-ttu-id="2be9a-185">Der Vertrag ist unabhängig vom Typ des Importobjekts.</span><span class="sxs-lookup"><span data-stu-id="2be9a-185">The contract is independent from the type of the importing object.</span></span>  <span data-ttu-id="2be9a-186">(In diesem Fall kann `typeof(ICalculator)` ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-186">(In this case, you could leave out the `typeof(ICalculator)`.</span></span>  <span data-ttu-id="2be9a-187">Sofern nicht anders angeben, wird von MEF automatisch angenommen, dass es sich um einen importtypbasierten Vertrag handelt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-187">MEF will automatically assume the contract to be based on the type of the import unless you specify it explicitly.)</span></span>  
  
 <span data-ttu-id="2be9a-188">Fügen Sie dem Modul oder dem `SimpleCalculator`-Namespace diese sehr einfache Schnittstelle hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-188">Add this very simple interface to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
Public Interface ICalculator  
    Function Calculate(ByVal input As String) As String  
End Interface  
```  
  
```csharp  
public interface ICalculator  
{  
    String Calculate(String input);  
}  
```  
  
 <span data-ttu-id="2be9a-189">Nach der Definition von `ICalculator` benötigen wir eine Klasse für die Implementierung.</span><span class="sxs-lookup"><span data-stu-id="2be9a-189">Now that you have defined `ICalculator`, you need a class that implements it.</span></span>  <span data-ttu-id="2be9a-190">Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgende Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-190">Add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(ICalculator))>  
Public Class MySimpleCalculator  
   Implements ICalculator  
  
End Class  
```  
  
```csharp  
[Export(typeof(ICalculator))]  
class MySimpleCalculator : ICalculator  
{  
  
}  
```  
  
 <span data-ttu-id="2be9a-191">Dieser Export entspricht dem Import in `Program`.</span><span class="sxs-lookup"><span data-stu-id="2be9a-191">Here is the export that will match the import in `Program`.</span></span> <span data-ttu-id="2be9a-192">Damit eine Übereinstimmung zwischen Export und Import vorliegt, muss der Export den gleichen Vertragstyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-192">In order for the export to match the import, the export must have the same contract.</span></span>  <span data-ttu-id="2be9a-193">Beim Export unter einem Vertrag auf Grundlage von `typeof(MySimpleCalculator)` wäre ein Konflikt die Folge, und der Import würde nicht ausgefüllt werden. Der Vertrag muss genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-193">Exporting under a contract based on `typeof(MySimpleCalculator)` would produce a mismatch, and the import would not be filled; the contract needs to match exactly.</span></span>  
  
 <span data-ttu-id="2be9a-194">Da der Kompositionscontainer alle in dieser Assembly verfügbaren Teilen enthält, ist der `MySimpleCalculator`-Teil verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2be9a-194">Since the composition container will be populated with all the parts available in this assembly, the `MySimpleCalculator` part will be available.</span></span>  <span data-ttu-id="2be9a-195">Wenn der Konstruktor für `Program` eine Komposition für das `Program`-Objekt ausführt, wird der entsprechende Import mit einem zu diesem Zweck erstellten `MySimpleCalculator`-Objekt ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-195">When the constructor for `Program` performs composition on the `Program` object, its import will be filled with a `MySimpleCalculator` object, which will be created for that purpose.</span></span>  
  
 <span data-ttu-id="2be9a-196">Für die Benutzeroberflächenebene (`Program`) müssen keine weiteren Informationen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-196">The user interface layer (`Program`) does not need to know anything else.</span></span>  <span data-ttu-id="2be9a-197">Sie können daher den Rest der Benutzeroberflächenlogik in der `Main`-Methode ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-197">You can therefore fill in the rest of the user interface logic in the `Main` method.</span></span>  
  
 <span data-ttu-id="2be9a-198">Fügen Sie der `Main`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-198">Add the following code to the `Main` method:</span></span>  
  
```vb  
Sub Main()  
    Dim p As New Program()  
    Dim s As String  
    Console.WriteLine("Enter Command:")  
    While (True)  
        s = Console.ReadLine()  
        Console.WriteLine(p.calculator.Calculate(s))  
    End While  
End Sub  
```  
  
```csharp  
static void Main(string[] args)  
{  
    Program p = new Program(); //Composition is performed in the constructor  
    String s;  
    Console.WriteLine("Enter Command:");  
    while (true)  
    {  
        s = Console.ReadLine();  
        Console.WriteLine(p.calculator.Calculate(s));  
    }  
}  
```  
  
 <span data-ttu-id="2be9a-199">Durch diesen Code wird lediglich eine Eingabezeile gelesen und die `Calculate`-Funktion von `ICalculator` für das Ergebnis aufgerufen, das an die Konsole zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2be9a-199">This code simply reads a line of input and calls the `Calculate` function of `ICalculator` on the result, which it writes back to the console.</span></span> <span data-ttu-id="2be9a-200">Mehr Code ist in `Program` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2be9a-200">That is all the code you need in `Program`.</span></span>  <span data-ttu-id="2be9a-201">Die restlichen Aufgaben werden in den Teilen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-201">All the rest of the work will happen in the parts.</span></span>  
  
<a name="further_imports_and_importmany"></a>   
## <a name="further-imports-and-importmany"></a><span data-ttu-id="2be9a-202">Weitere Importe und ImportMany</span><span class="sxs-lookup"><span data-stu-id="2be9a-202">Further Imports and ImportMany</span></span>  
 <span data-ttu-id="2be9a-203">Zur Gewährleistung der Erweiterbarkeit von SimpleCalculator muss eine Reihe von Vorgängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-203">In order for SimpleCalculator to be extensible, it needs to import a list of operations.</span></span> <span data-ttu-id="2be9a-204">Ein gewöhnliches <xref:System.ComponentModel.Composition.ImportAttribute>-Attribut wird von ausschließlich einem <xref:System.ComponentModel.Composition.ExportAttribute> ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-204">An ordinary <xref:System.ComponentModel.Composition.ImportAttribute> attribute is filled by one and only one <xref:System.ComponentModel.Composition.ExportAttribute>.</span></span>  <span data-ttu-id="2be9a-205">Sind mehrere Exporte verfügbar, wird von der Kompositions-Engine ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2be9a-205">If more than one is available, the composition engine produces an error.</span></span>  <span data-ttu-id="2be9a-206">Zur Erstellung eines Imports, der mit einer beliebigen Anzahl von Exporten ausgefüllt werden kann, verwenden Sie das <xref:System.ComponentModel.Composition.ImportManyAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="2be9a-206">To create an import that can be filled by any number of exports, you can use the <xref:System.ComponentModel.Composition.ImportManyAttribute> attribute.</span></span>  
  
 <span data-ttu-id="2be9a-207">Fügen Sie der `MySimpleCalculator`-Klasse die folgende Eigenschaft für Vorgänge hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-207">Add the following operations property to the `MySimpleCalculator` class:</span></span>  
  
```vb  
<ImportMany()>  
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))  
```  
  
```csharp  
[ImportMany]  
IEnumerable<Lazy<IOperation, IOperationData>> operations;  
```  
  
 <span data-ttu-id="2be9a-208"><xref:System.Lazy%602> ist ein von MEF bereitgestellter Typ für indirekte Verweise auf Exporte.</span><span class="sxs-lookup"><span data-stu-id="2be9a-208"><xref:System.Lazy%602> is a type provided by MEF to hold indirect references to exports.</span></span>  <span data-ttu-id="2be9a-209">Zusätzlich zum exportierten Objekt selbst können hier auch *Exportmetadaten* oder Informationen abgerufen werden, die das exportierte Objekt beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2be9a-209">Here, in addition to the exported object itself, you also get *export metadata*, or information that describes the exported object.</span></span> <span data-ttu-id="2be9a-210">Jeder <xref:System.Lazy%602> enthält ein `IOperation`-Objekt, das eine tatsächliche Operation darstellt, und ein `IOperationData`-Objekt, das die Metadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-210">Each <xref:System.Lazy%602> contains an `IOperation` object, representing an actual operation, and an `IOperationData` object, representing its metadata.</span></span>  
  
 <span data-ttu-id="2be9a-211">Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgenden einfachen Schnittstellen hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-211">Add the following simple interfaces to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
Public Interface IOperation  
    Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer  
End Interface  
  
Public Interface IOperationData  
    ReadOnly Property Symbol As Char  
End Interface  
```  
  
```csharp  
public interface IOperation  
{  
     int Operate(int left, int right);  
}  
  
public interface IOperationData  
{  
    Char Symbol { get; }  
}  
```  
  
 <span data-ttu-id="2be9a-212">In diesem Fall handelt es sich bei den Metadaten für die einzelnen Vorgänge um das Symbol, das diese Operation darstellt, z. B. +, -, \* usw.</span><span class="sxs-lookup"><span data-stu-id="2be9a-212">In this case, the metadata for each operation is the symbol that represents that operation, such as +, -, \*, and so on.</span></span> <span data-ttu-id="2be9a-213">Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgende Klasse hinzu, um die Additionsoperation verfügbar zu machen:</span><span class="sxs-lookup"><span data-stu-id="2be9a-213">To make the addition operation available, add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(IOperation))>  
<ExportMetadata("Symbol", "+"c)>  
Public Class Add  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left + right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(IOperation))]  
[ExportMetadata("Symbol", '+')]  
class Add: IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left + right;  
    }  
}  
```  
  
 <span data-ttu-id="2be9a-214">An der Funktionsweise des <xref:System.ComponentModel.Composition.ExportAttribute>-Attributs hat sich nichts geändert.</span><span class="sxs-lookup"><span data-stu-id="2be9a-214">The <xref:System.ComponentModel.Composition.ExportAttribute> attribute functions as it did before.</span></span>  <span data-ttu-id="2be9a-215">Das <xref:System.ComponentModel.Composition.ExportMetadataAttribute>-Attribut fügt dem Export Metadaten in Form eines Name-Wert-Paars hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-215">The <xref:System.ComponentModel.Composition.ExportMetadataAttribute> attribute attaches metadata, in the form of a name-value pair, to that export.</span></span>  <span data-ttu-id="2be9a-216">`Add` wird zwar von der `IOperation`-Klasse implementiert; eine Klasse, die `IOperationData` implementiert, wurde jedoch nicht explizit definiert.</span><span class="sxs-lookup"><span data-stu-id="2be9a-216">While the `Add` class implements `IOperation`, a class that implements `IOperationData` is not explicitly defined.</span></span> <span data-ttu-id="2be9a-217">Stattdessen wird eine Klasse, deren Eigenschaften auf den Namen der bereitgestellten Metadaten basieren, implizit von MEF erstellt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-217">Instead, a class is implicitly created by MEF with properties based on the names of the metadata provided.</span></span>  <span data-ttu-id="2be9a-218">(Dies ist eine von mehreren Möglichkeiten für den Zugriff auf Metadaten in MEF.)</span><span class="sxs-lookup"><span data-stu-id="2be9a-218">(This is one of several ways to access metadata in MEF.)</span></span>  
  
 <span data-ttu-id="2be9a-219">Die Komposition in MEF ist *rekursiv*.</span><span class="sxs-lookup"><span data-stu-id="2be9a-219">Composition in MEF is *recursive*.</span></span> <span data-ttu-id="2be9a-220">Sie haben das `Program`-Objekt, durch das ein `ICalculator` vom Typ `MySimpleCalculator` importiert wurde, explizit zusammengesetzt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-220">You explicitly composed the `Program` object, which imported an `ICalculator` that turned out to be of type `MySimpleCalculator`.</span></span>  <span data-ttu-id="2be9a-221">Von `MySimpleCalculator` wird wiederum eine Auflistung von `IOperation`-Objekten importiert. Dieser Import wird zur gleichen Zeit wie die Importe von `MySimpleCalculator` bei der Erstellung von `Program` ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-221">`MySimpleCalculator`, in turn, imports a collection of `IOperation` objects, and that import will be filled when `MySimpleCalculator` is created, at the same time as the imports of `Program`.</span></span> <span data-ttu-id="2be9a-222">Würde von der `Add`-Klasse ein weiterer Import deklariert werden, würde dieser ebenfalls ausgefüllt werden müssen usw.</span><span class="sxs-lookup"><span data-stu-id="2be9a-222">If the `Add` class declared a further import, that too would have to be filled, and so on.</span></span> <span data-ttu-id="2be9a-223">Jeder nicht ausgefüllte Import führt zu einem Fehler bei der Komposition.</span><span class="sxs-lookup"><span data-stu-id="2be9a-223">Any import left unfilled results in a composition error.</span></span>  <span data-ttu-id="2be9a-224">(Es ist jedoch möglich, Importe als optional zu deklarieren oder ihnen Standardwerte zuzuweisen.)</span><span class="sxs-lookup"><span data-stu-id="2be9a-224">(It is possible, however, to declare imports to be optional or to assign them default values.)</span></span>  
  
<a name="calculator_logic"></a>   
## <a name="calculator-logic"></a><span data-ttu-id="2be9a-225">Rechnerlogik</span><span class="sxs-lookup"><span data-stu-id="2be9a-225">Calculator Logic</span></span>  
 <span data-ttu-id="2be9a-226">Sind diese Teile bereitgestellt, bleibt nun noch die Rechnerlogik selbst.</span><span class="sxs-lookup"><span data-stu-id="2be9a-226">With these parts in place, all that remains is the calculator logic itself.</span></span> <span data-ttu-id="2be9a-227">Fügen Sie der `MySimpleCalculator`-Klasse den folgenden Code hinzu, um die `Calculate`-Methode zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="2be9a-227">Add the following code in the `MySimpleCalculator` class to implement the `Calculate` method:</span></span>  
  
```vb  
Public Function Calculate(ByVal input As String) As String Implements ICalculator.Calculate  
    Dim left, right As Integer  
    Dim operation As Char  
    Dim fn = FindFirstNonDigit(input) 'Finds the operator  
    If fn < 0 Then  
        Return "Could not parse command."  
    End If  
    operation = input(fn)  
    Try  
        left = Integer.Parse(input.Substring(0, fn))  
        right = Integer.Parse(input.Substring(fn + 1))  
    Catch ex As Exception  
        Return "Could not parse command."  
    End Try  
    For Each i As Lazy(Of IOperation, IOperationData) In operations  
        If i.Metadata.symbol = operation Then  
            Return i.Value.Operate(left, right).ToString()  
        End If  
    Next  
    Return "Operation not found!"  
End Function  
```  
  
```csharp  
public String Calculate(String input)  
{  
    int left;  
    int right;  
    Char operation;  
    int fn = FindFirstNonDigit(input); //finds the operator  
    if (fn < 0) return "Could not parse command.";  
  
    try  
    {  
        //separate out the operands  
        left = int.Parse(input.Substring(0, fn));  
        right = int.Parse(input.Substring(fn + 1));  
    }  
    catch   
    {  
        return "Could not parse command.";  
    }  
  
    operation = input[fn];  
  
    foreach (Lazy<IOperation, IOperationData> i in operations)  
    {  
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();  
    }  
    return "Operation Not Found!";  
}  
```  
  
 <span data-ttu-id="2be9a-228">Durch die anfänglichen Schritte wird die Eingabezeichenfolge analysiert und in linke und rechte Operanden sowie in ein Operatorzeichen eingeteilt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-228">The initial steps parse the input string into left and right operands and an operator character.</span></span>  <span data-ttu-id="2be9a-229">In der `foreach`-Schleife wird jeder Member der `operations`-Auflistung untersucht.</span><span class="sxs-lookup"><span data-stu-id="2be9a-229">In the `foreach` loop, every member of the `operations` collection is examined.</span></span> <span data-ttu-id="2be9a-230">Diese Objekte sind vom Typ <xref:System.Lazy%602>, und der Zugriff auf die Metadatenwerte und das exportierte Objekt ist mit der <xref:System.Lazy%602.Metadata%2A>- bzw. <xref:System.Lazy%601.Value%2A>-Eigenschaft möglich.</span><span class="sxs-lookup"><span data-stu-id="2be9a-230">These objects are of type <xref:System.Lazy%602>, and their metadata values and exported object can be accessed with the <xref:System.Lazy%602.Metadata%2A> property and the <xref:System.Lazy%601.Value%2A> property respectively.</span></span> <span data-ttu-id="2be9a-231">Wird in diesem Fall festgestellt, dass es sich bei der `Symbol`-Eigenschaft des `IOperationData`-Objekts um eine Übereinstimmung handelt, ruft der Rechner die `Operate`-Methode des `IOperation`-Objekts auf und gibt das Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="2be9a-231">In this case, if the `Symbol` property of the `IOperationData` object is discovered to be a match, the calculator calls the `Operate` method of the `IOperation` object and returns the result.</span></span>  
  
 <span data-ttu-id="2be9a-232">Zur Fertigstellung des Rechners benötigen Sie auch eine Hilfsmethode, die die Position des ersten Zeichens einer Zeichenfolge zurückgibt, bei dem es sich nicht um eine Ziffer handelt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-232">To complete the calculator, you also need a helper method that returns the position of the first non-digit character in a string.</span></span>  <span data-ttu-id="2be9a-233">Fügen Sie der `MySimpleCalculator`-Klasse die folgende Hilfsmethode hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-233">Add the following helper method to the `MySimpleCalculator` class:</span></span>  
  
```vb  
Private Function FindFirstNonDigit(ByVal s As String) As Integer  
    For i = 0 To s.Length  
        If (Not (Char.IsDigit(s(i)))) Then Return i  
    Next  
    Return -1  
End Function  
```  
  
```csharp  
private int FindFirstNonDigit(String s)  
{  
    for (int i = 0; i < s.Length; i++)  
    {  
        if (!(Char.IsDigit(s[i]))) return i;  
    }  
    return -1;  
}  
```  
  
 <span data-ttu-id="2be9a-234">Sie sollten das Datenbankprojekt jetzt kompilieren und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="2be9a-234">You should now be able to compile and run the project.</span></span> <span data-ttu-id="2be9a-235">In Visual Basic müssen Sie sicherstellen, dass Sie `Public` das Schlüsselwort `Module1` hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="2be9a-235">In Visual Basic, make sure that you added the `Public` keyword to `Module1`.</span></span> <span data-ttu-id="2be9a-236">Geben Sie im Konsolenfenster eine Addition ein, z. B. "5+3", und der Rechner gibt das entsprechende Ergebnis aus.</span><span class="sxs-lookup"><span data-stu-id="2be9a-236">In the console window, type an addition operation, such as "5+3", and the calculator will return the results.</span></span>  <span data-ttu-id="2be9a-237">Ein beliebiger anderer Operator führt zu einer Meldung, die anzeigt, dass der</span><span class="sxs-lookup"><span data-stu-id="2be9a-237">Any other operator will result in the "Operation Not Found!"</span></span> <span data-ttu-id="2be9a-238">Vorgang nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="2be9a-238">message.</span></span>  
  
<a name="extending_simplecalculator_using_a_new_class"></a>   
## <a name="extending-simplecalculator-using-a-new-class"></a><span data-ttu-id="2be9a-239">Erweitern von SimpleCalculator mithilfe einer neuen Klasse</span><span class="sxs-lookup"><span data-stu-id="2be9a-239">Extending SimpleCalculator Using A New Class</span></span>  
 <span data-ttu-id="2be9a-240">Da der Rechner nun funktioniert, kann ganz leicht eine neue Rechenoperation hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-240">Now that the calculator works, adding a new operation is easy.</span></span> <span data-ttu-id="2be9a-241">Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgende Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-241">Add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(IOperation))>  
<ExportMetadata("Symbol", "-"c)>  
Public Class Subtract  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left - right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(IOperation))]  
[ExportMetadata("Symbol", '-')]  
class Subtract : IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left - right;  
    }  
}  
```  
  
 <span data-ttu-id="2be9a-242">Kompilieren Sie das Projekt und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="2be9a-242">Compile and run the project.</span></span> <span data-ttu-id="2be9a-243">Geben Sie eine Subtraktion ein, z. B. "5-3".</span><span class="sxs-lookup"><span data-stu-id="2be9a-243">Type a subtraction operation, such as "5-3".</span></span> <span data-ttu-id="2be9a-244">Der Rechner unterstützt jetzt Subtraktionen ebenso sowie Additionen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-244">The calculator now supports subtraction as well as addition.</span></span>  
  
<a name="extending_simplecalculator_using_a_new_assembly"></a>   
## <a name="extending-simplecalculator-using-a-new-assembly"></a><span data-ttu-id="2be9a-245">Erweitern von SimpleCalculator mithilfe einer neuen Assembly</span><span class="sxs-lookup"><span data-stu-id="2be9a-245">Extending SimpleCalculator Using A New Assembly</span></span>  
 <span data-ttu-id="2be9a-246">Das Hinzufügen von Klassen zum Quellcode ist einfach, aber mit MEF kann auch außerhalb des Quellcodes einer Anwendung nach Teilen gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-246">Adding classes to the source code is simple enough, but MEF provides the ability to look outside an application’s own source for parts.</span></span> <span data-ttu-id="2be9a-247">Zur Veranschaulichung muss SimpleCalculator für die Suche nach Teilen in Verzeichnissen und in seinen eigenen Assemblys durch das Hinzufügen eines <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-247">To demonstrate this, you will need to modify SimpleCalculator to search a directory, as well as its own assembly, for parts, by adding a <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span></span>  
  
 <span data-ttu-id="2be9a-248">Fügen Sie dem SimpleCalculator-Projekt ein neues Verzeichnis mit dem Namen `Extensions` hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-248">Add a new directory named `Extensions` to the SimpleCalculator project.</span></span>  <span data-ttu-id="2be9a-249">Das Verzeichnis muss auf der Projektebene und nicht auf der Projektmappenebene hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-249">Make sure to add it at the project level, and not at the solution level.</span></span> <span data-ttu-id="2be9a-250">Fügen Sie der Projektmappe anschließend ein neues ClassLibrary-Projekt mit dem Namen `ExtendedOperations` hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-250">Then add a new Class Library project to the solution, named `ExtendedOperations`.</span></span> <span data-ttu-id="2be9a-251">Das neue Projekt wird in eine separate Assembly kompiliert.</span><span class="sxs-lookup"><span data-stu-id="2be9a-251">The new project will compile into a separate assembly.</span></span>  
  
 <span data-ttu-id="2be9a-252">Öffnen Sie den Projekteigenschaften-Designer für das ExtendedOperations-Projekt, und klicken Sie auf die Registerkarte **Erstellen** oder auf die Registerkarte **Kompilieren**. Ändern Sie den **Buildausgabepfad** oder den **Ausgabepfad**, sodass dieser auf das Erweiterungsverzeichnis im SimpleCalculator-Projektverzeichnis zeigt (..\SimpleCalculator\Extensions\\).</span><span class="sxs-lookup"><span data-stu-id="2be9a-252">Open the Project Properties Designer for the ExtendedOperations project and click the **Compile** or **Build** tab. Change the **Build output path** or **Output path** to point to the Extensions directory in the SimpleCalculator project directory (..\SimpleCalculator\Extensions\\).</span></span>  
  
 <span data-ttu-id="2be9a-253">Fügen Sie anschließend dem `Program`-Konstruktor in der Datei Module1.vb oder in der Datei "Program.cs" die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-253">In Module1.vb or Program.cs, add the following line to the `Program` constructor:</span></span>  
  
```vb  
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))  
```  
  
```csharp  
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));  
```  
  
 <span data-ttu-id="2be9a-254">Ersetzen Sie den Beispielpfad durch den Pfad zum Verzeichnis "Erweiterungen".</span><span class="sxs-lookup"><span data-stu-id="2be9a-254">Replace the example path with the path to your Extensions directory.</span></span>  <span data-ttu-id="2be9a-255">(Dieser absolute Pfad ist nur für Debugzwecke bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-255">(This absolute path is for debugging purposes only.</span></span>  <span data-ttu-id="2be9a-256">In einer Produktionsanwendung würde ein relativer Pfad verwendet werden.) Vom <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> werden jetzt alle in den Assemblys im Verzeichnis "Erweiterungen" enthaltenen Teile dem Kompositionscontainer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-256">In a production application, you would use a relative path.) The <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> will now add any parts found in any assemblies in the Extensions directory to the composition container.</span></span>  
  
 <span data-ttu-id="2be9a-257">Fügen Sie im ExtendedOperations-Projekt Verweise auf SimpleCalculator und System.ComponentModel.Composition hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-257">In the ExtendedOperations project, add references to SimpleCalculator and System.ComponentModel.Composition.</span></span> <span data-ttu-id="2be9a-258">Fügen Sie in der ExtendedOperations-Klassendatei eine `Imports`- oder eine `using`-Anweisung für System.ComponentModel.Composition hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-258">In the ExtendedOperations class file, add an `Imports` or a `using` statement for System.ComponentModel.Composition.</span></span> <span data-ttu-id="2be9a-259">Fügen Sie in Visual Basic die `Imports`-Anweisung für SimpleCalculator hinzu.</span><span class="sxs-lookup"><span data-stu-id="2be9a-259">In Visual Basic, also add an `Imports` statement for SimpleCalculator.</span></span> <span data-ttu-id="2be9a-260">Fügen Sie der ExtendedOperations-Klassendatei anschließend den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2be9a-260">Then add the following class to the ExtendedOperations class file:</span></span>  
  
```vb  
<Export(GetType(SimpleCalculator.IOperation))>  
<ExportMetadata("Symbol", "%"c)>  
Public Class Modulo  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left Mod right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(SimpleCalculator.IOperation))]  
[ExportMetadata("Symbol", '%')]  
public class Mod : SimpleCalculator.IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left % right;  
    }  
}  
```  
  
 <span data-ttu-id="2be9a-261">Das <xref:System.ComponentModel.Composition.ExportAttribute>-Attribut muss vom gleichen Typ sein wie <xref:System.ComponentModel.Composition.ImportAttribute>, damit der Vertrag als Übereinstimmung betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="2be9a-261">Note that in order for the contract to match, the <xref:System.ComponentModel.Composition.ExportAttribute> attribute must have the same type as the <xref:System.ComponentModel.Composition.ImportAttribute>.</span></span>  
  
 <span data-ttu-id="2be9a-262">Kompilieren Sie das Projekt und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="2be9a-262">Compile and run the project.</span></span> <span data-ttu-id="2be9a-263">Testen Sie den neuen MOD (%)-Operator.</span><span class="sxs-lookup"><span data-stu-id="2be9a-263">Test the new Mod (%) operator.</span></span>  
  
<a name="conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="2be9a-264">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="2be9a-264">Conclusion</span></span>  
 <span data-ttu-id="2be9a-265">In diesem Thema wurden die grundlegenden Konzepte des MEF behandelt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-265">This topic covered the basic concepts of MEF.</span></span>  
  
-   <span data-ttu-id="2be9a-266">Teile, Kataloge und der Kompositionscontainer</span><span class="sxs-lookup"><span data-stu-id="2be9a-266">Parts, catalogs, and the composition container</span></span>  
  
     <span data-ttu-id="2be9a-267">Die Teile und der Kompositionscontainer sind die Grundbausteine einer MEF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2be9a-267">Parts and the composition container are the basic building blocks of a MEF application.</span></span> <span data-ttu-id="2be9a-268">Ein Teil ist jedes Objekt, durch das ein Wert importiert oder exportiert wird, einschließlich des Objekts selbst.</span><span class="sxs-lookup"><span data-stu-id="2be9a-268">A part is any object that imports or exports a value, up to and including itself.</span></span> <span data-ttu-id="2be9a-269">Ein Katalog stellt eine Auflistung der Teile einer bestimmten Quelle bereit.</span><span class="sxs-lookup"><span data-stu-id="2be9a-269">A catalog provides a collection of parts from a particular source.</span></span>  <span data-ttu-id="2be9a-270">Der Kompositionscontainer verwendet die von einem Katalog bereitgestellten Teile, um eine Komposition (die Bindung von Importen an Exporte) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-270">The composition container uses the parts provided by a catalog to perform composition, the binding of imports to exports.</span></span>  
  
-   <span data-ttu-id="2be9a-271">Importe und Exporte</span><span class="sxs-lookup"><span data-stu-id="2be9a-271">Imports and exports</span></span>  
  
     <span data-ttu-id="2be9a-272">Durch Importe und Exporte kommunizieren Komponenten miteinander.</span><span class="sxs-lookup"><span data-stu-id="2be9a-272">Imports and exports are the way by which components communicate.</span></span> <span data-ttu-id="2be9a-273">Durch einen Import fordert eine Komponente einen bestimmten Wert oder ein Objekt an. Mit einem Export wird die Verfügbarkeit eines Werts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2be9a-273">With an import, the component specifies a need for a particular value or object, and with an export it specifies the availability of a value.</span></span> <span data-ttu-id="2be9a-274">Jeder Import wird anhand seines Vertrags mit einer Reihe von Exporten verglichen.</span><span class="sxs-lookup"><span data-stu-id="2be9a-274">Each import is matched with a list of exports by way of its contract.</span></span>  
  
<a name="where_do_i_go_now"></a>   
## <a name="where-do-i-go-now"></a><span data-ttu-id="2be9a-275">Wo soll ich fortfahren?</span><span class="sxs-lookup"><span data-stu-id="2be9a-275">Where Do I Go Now?</span></span>  
 <span data-ttu-id="2be9a-276">Der vollständige Code für dieses Beispiel kann unter [SimpleCalculator-Beispiel](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="2be9a-276">To download the complete code for this example, see the [SimpleCalculator sample](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span></span>  
  
 <span data-ttu-id="2be9a-277">Weitere Informationen und Codebeispiele finden Sie unter [Managed Extensibility Framework](https://go.microsoft.com/fwlink/?LinkId=144282).</span><span class="sxs-lookup"><span data-stu-id="2be9a-277">For more information and code examples, see [Managed Extensibility Framework](https://go.microsoft.com/fwlink/?LinkId=144282).</span></span> <span data-ttu-id="2be9a-278">Eine Liste der MEF-Typen finden Sie unter dem <xref:System.ComponentModel.Composition?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="2be9a-278">For a list of the MEF types, see the <xref:System.ComponentModel.Composition?displayProperty=nameWithType> namespace.</span></span>
