---
title: Wichtige Änderungen und Bibliotheken für .NET
description: Empfehlungen für bewährte Methoden navigieren, wichtige Änderungen, wenn Sie Bibliotheken für .NET zu erstellen.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370063"
---
# <a name="breaking-changes"></a><span data-ttu-id="5cfec-103">Wichtige Änderungen</span><span class="sxs-lookup"><span data-stu-id="5cfec-103">Breaking changes</span></span>

<span data-ttu-id="5cfec-104">Es ist wichtig für die eine .NET-Bibliothek finden Sie ein Gleichgewicht zwischen Stabilität für vorhandene Benutzer und Innovationen für die Zukunft.</span><span class="sxs-lookup"><span data-stu-id="5cfec-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="5cfec-105">Autoren von Klassenbibliotheken erfahren Sie, für die Umgestaltung und neuer Ansatz für Code, bis er sich hervorragend eignet, aber Ihre vorhandenen Benutzer wichtige negative Auswirkungen, insbesondere für Low-Level-Bibliotheken hat.</span><span class="sxs-lookup"><span data-stu-id="5cfec-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="5cfec-106">Projekttypen und wichtige Änderungen</span><span class="sxs-lookup"><span data-stu-id="5cfec-106">Project types and breaking changes</span></span>

<span data-ttu-id="5cfec-107">Die Auswirkungen der Änderungen für endbenutzerentwickler, die durch den ändert sich wie eine Bibliothek von der .NET-Community zuzog verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5cfec-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

* <span data-ttu-id="5cfec-108">**Niedrig und mittleren Stufe Bibliotheken** wie ein Serialisierungsprogramm, HTML-Parser, objektrelationale Zuordnung Datenbank oder Web-Framework sind die betroffenen wichtige Änderungen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="5cfec-109">Baustein-Pakete werden als NuGet-Abhängigkeiten von Endbenutzer-Entwicklern zum Erstellen von Anwendungen und von anderen Bibliotheken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5cfec-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="5cfec-110">Z. B. Sie eine Anwendung entwickeln und einen Open-Source-Client auf einen Webdienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="5cfec-111">Eine wichtige-Update für eine Abhängigkeit, die der Client verwendet, nicht, die Sie beheben können.</span><span class="sxs-lookup"><span data-stu-id="5cfec-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="5cfec-112">Es ist der Open-Source-Client, der geändert werden muss, und Sie haben keine Kontrolle darüber.</span><span class="sxs-lookup"><span data-stu-id="5cfec-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="5cfec-113">Sie müssen kompatible Versionen der Bibliotheken finden oder senden eine Lösung für die Clientbibliothek, und warten, bis eine neue Version.</span><span class="sxs-lookup"><span data-stu-id="5cfec-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="5cfec-114">Den schlimmsten Fall ist, sollten Sie zwei Bibliotheken verwenden, die auf inkompatible Versionen von einer dritten-Bibliothek abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="5cfec-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

* <span data-ttu-id="5cfec-115">**Allgemeine Bibliotheken** wie eine Sammlung von UI-Steuerelemente sind weniger anfällig für wichtige Änderungen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="5cfec-116">Allgemeine Bibliotheken werden direkt in einer endbenutzeranwendung auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5cfec-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="5cfec-117">Wenn Änderungen auftreten, wird der Entwickler kann auch auf die neueste Version zu aktualisieren, oder Ändern ihrer Anwendung zur Zusammenarbeit mit der grundlegenden Änderungen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="5cfec-118">**Führen Sie ✔️** überlegen, wie die Bibliothek verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5cfec-118">**✔️ DO** think about how your library will be used.</span></span> <span data-ttu-id="5cfec-119">Welche Auswirkungen haben wichtige Änderungen auf Anwendungen und Bibliotheken, die sie verwenden?</span><span class="sxs-lookup"><span data-stu-id="5cfec-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="5cfec-120">**Führen Sie ✔️** Änderungen minimiert werden, wenn eine .NET-Bibliothek auf niedriger Ebene zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="5cfec-120">**✔️ DO** minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="5cfec-121">**✔️ GGF.** veröffentlichen eine größere schreiben, einer Bibliothek als neue NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="5cfec-121">**✔️ CONSIDER** publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="5cfec-122">Arten von Änderungen</span><span class="sxs-lookup"><span data-stu-id="5cfec-122">Types of breaking changes</span></span>

<span data-ttu-id="5cfec-123">Wichtige Änderungen in verschiedene Kategorien fallen, und es sind nicht gleichmäßig eindrucksvolle.</span><span class="sxs-lookup"><span data-stu-id="5cfec-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="5cfec-124">Wichtige Änderung an der Datenquelle</span><span class="sxs-lookup"><span data-stu-id="5cfec-124">Source breaking change</span></span>

<span data-ttu-id="5cfec-125">Eine Quelle, die wichtige Änderung führt betrifft keine Ausführung des Programms aber zu Kompilierungsfehler das nächste Mal, die, das die Anwendung erneut kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="5cfec-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="5cfec-126">Z. B. eine neue Überladung kann eine Mehrdeutigkeit in Methodenaufrufe, die eindeutig früher erstellen, oder ein umbenannter Parameter unterbricht Aufrufer, mit denen benannte Parameter.</span><span class="sxs-lookup"><span data-stu-id="5cfec-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="5cfec-127">Da es sich bei eine Quelle, die wichtige Änderung nur schädlich ist, wenn Entwickler ihre Anwendungen neu kompilieren, ist es am wenigsten störenden wichtige Änderung.</span><span class="sxs-lookup"><span data-stu-id="5cfec-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="5cfec-128">Entwickler können ihre eigenen unterbrochen Quellcode einfach beheben.</span><span class="sxs-lookup"><span data-stu-id="5cfec-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="5cfec-129">Wichtige verhaltensänderung</span><span class="sxs-lookup"><span data-stu-id="5cfec-129">Behavior breaking change</span></span>

<span data-ttu-id="5cfec-130">Verändertes Programmverhalten sind der am häufigsten verwendeten wichtige Änderung: nahezu jede Änderung im Verhalten kann ein Benutzer unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="5cfec-131">Änderungen an Ihrer Bibliothek, z. B. Methodensignaturen Ausnahmen ausgelöst oder Eingabe oder Ausgabe Datenformate, könnten alle beeinträchtigt Ihre Consumer.</span><span class="sxs-lookup"><span data-stu-id="5cfec-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="5cfec-132">Als fehlerhafte Änderung können sogar eine Programmfehlerbehebung qualifizieren, wenn Benutzer auf das zuvor fehlerhaften Verhalten beruhte.</span><span class="sxs-lookup"><span data-stu-id="5cfec-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="5cfec-133">Hinzufügen von Funktionen und schlechte Verhaltensweisen verbessern, ist eine gute Sache, aber ohne Sorgfalt können erleichtern es sehr schwierig für vorhandene Benutzer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5cfec-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="5cfec-134">Ein Ansatz zum Schutz von Entwicklern, die Behandlung von Verhalten, die wichtige Änderungen werden hinter Einstellungen ausblenden.</span><span class="sxs-lookup"><span data-stu-id="5cfec-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="5cfec-135">Einstellungen können Entwickler auf die neueste Version Ihrer Bibliothek, während gleichzeitig auswählen, aktivieren oder deaktivieren die Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5cfec-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="5cfec-136">Diese Strategie ermöglicht Entwicklern, die auf dem neuesten Stand zu bleiben, während ihre verwendeten Code im Laufe der Zeit anpassen lassen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="5cfec-137">Beispielsweise ASP.NET Core MVC hat das Konzept einer [Kompatibilitätsversion](/aspnet/core/mvc/compatibility-version) , ändert es sich um die Funktionen aktiviert und deaktiviert auf `MvcOptions`.</span><span class="sxs-lookup"><span data-stu-id="5cfec-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="5cfec-138">**✔️ GGF.** neue Features in der Standardeinstellung deaktiviert verlassen, wenn sie die Auswirkungen auf vorhandene Benutzer, und Entwicklern, die ermöglichen sich auf die Funktion mit einer Einstellung entscheiden.</span><span class="sxs-lookup"><span data-stu-id="5cfec-138">**✔️ CONSIDER** leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="5cfec-139">Binäre unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="5cfec-139">Binary breaking change</span></span>

<span data-ttu-id="5cfec-140">Eine wichtige Änderung Binärdatei tritt auf, wenn Sie die öffentliche API Ihrer Bibliothek ändern, damit Assemblys kompiliert ältere Versionen Ihrer Bibliothek können nicht mehr zum Aufrufen der API.</span><span class="sxs-lookup"><span data-stu-id="5cfec-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="5cfec-141">Beispielsweise ändern die Signatur einer Methode, durch Hinzufügen eines neuen Parameters führt dazu, dass Assemblys, die für die ältere Version der Bibliothek kompiliert, um auszulösen, eine <xref:System.MissingMethodException>.</span><span class="sxs-lookup"><span data-stu-id="5cfec-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="5cfec-142">Eine wichtige Änderung Binärdatei kann auch unterbrochen. eine **gesamte Assembly**.</span><span class="sxs-lookup"><span data-stu-id="5cfec-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="5cfec-143">Umbenennen einer Assembly mit `AssemblyName` ändert sich der Identität der Assembly, wie hinzufügen, entfernen oder ändern den Schlüssel der Assembly starke Benennung.</span><span class="sxs-lookup"><span data-stu-id="5cfec-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="5cfec-144">Eine Änderung der Identität einer Assembly werden alle kompilierten Code unterbrochen, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5cfec-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="5cfec-145">**❌ NICHT** Namen einer Assembly zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5cfec-145">**❌ DO NOT** change an assembly name.</span></span>

<span data-ttu-id="5cfec-146">**❌ NICHT** hinzufügen, entfernen oder ändern Sie den Schlüssel für starke benennungen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-146">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="5cfec-147">**✔️ GGF.** anstelle Schnittstellen von abstrakten Basisklassen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-147">**✔️ CONSIDER** using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="5cfec-148">Nichts hinzufügen, um eine Schnittstelle bewirkt vorhandene Typen, die Fehler zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="5cfec-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="5cfec-149">Eine abstrakte Basisklasse, können Sie eine Standardimplementierung für den virtuellen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="5cfec-150">**✔️ GGF.** Platzieren der <xref:System.ObsoleteAttribute> für Typen und Member, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="5cfec-150">**✔️ CONSIDER** placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="5cfec-151">Das Attribut müssen Anweisungen zum Aktualisieren von Code aus, um die veraltete API nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="5cfec-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="5cfec-152">Code, der Aufrufe von Typen und Methoden mit dem <xref:System.ObsoleteAttribute> wird eine Buildwarnung generiert, mit der Meldung, die für das Attribut angegebenen.</span><span class="sxs-lookup"><span data-stu-id="5cfec-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="5cfec-153">Warnungen bieten Personen, die beim veraltet-API-Oberfläche verwenden, migrieren, damit beim Entfernen der veralteten API die meisten nicht mehr sind Verwendung.</span><span class="sxs-lookup"><span data-stu-id="5cfec-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a><span data-ttu-id="5cfec-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cfec-154">See also</span></span>

* [<span data-ttu-id="5cfec-155">Überlegungen zur Version und Updates für C#-Entwickler</span><span class="sxs-lookup"><span data-stu-id="5cfec-155">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
* [<span data-ttu-id="5cfec-156">Endgültiger Leitfaden zur API-Änderungen in .NET</span><span class="sxs-lookup"><span data-stu-id="5cfec-156">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [<span data-ttu-id="5cfec-157">CoreFX wichtige Ändern der Regeln</span><span class="sxs-lookup"><span data-stu-id="5cfec-157">CoreFX Breaking Change Rules</span></span>](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[<span data-ttu-id="5cfec-158">Vorherige</span><span class="sxs-lookup"><span data-stu-id="5cfec-158">Previous</span></span>](./versioning.md)
