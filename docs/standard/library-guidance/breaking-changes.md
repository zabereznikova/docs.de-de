---
title: Breaking Changes und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Umgang mit Breaking Changes beim Erstellen von .NET-Bibliotheken.
ms.date: 10/02/2018
ms.openlocfilehash: 2cbd9e0a818b52aede6c9b1f60fdf52dcbd7b96f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731464"
---
# <a name="breaking-changes"></a><span data-ttu-id="aceb6-103">Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="aceb6-103">Breaking changes</span></span>

<span data-ttu-id="aceb6-104">Es ist wichtig für eine .NET-Bibliothek, ein Gleichgewicht zwischen Stabilität für bestehende Benutzer und Innovation für die Zukunft zu finden.</span><span class="sxs-lookup"><span data-stu-id="aceb6-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="aceb6-105">Ersteller von Bibliotheken verändern Code gelegentlich, bis er ihren Ansprüchen entspricht. Allerdings haben Unterbrechungen negative Auswirkungen auf Ihre Benutzer, besonders bei Bibliotheken auf niedriger Ebene.</span><span class="sxs-lookup"><span data-stu-id="aceb6-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="aceb6-106">Projekttypen und Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="aceb6-106">Project types and breaking changes</span></span>

<span data-ttu-id="aceb6-107">Wie eine Bibliothek von der .NET-Community verwendet wird, ändert die Auswirkungen von Breaking Changes auf die Endbenutzerentwickler.</span><span class="sxs-lookup"><span data-stu-id="aceb6-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

- <span data-ttu-id="aceb6-108">**Bibliotheken auf niedriger und mittlerer Ebene** wie Serialisierungsmodule, HTML-Parser, datenbankobjektrelationale Mapper oder Webframeworks sind am stärksten von Breaking Changes betroffen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="aceb6-109">Bausteinpakete werden von Endbenutzerentwicklern zum Erstellen von Anwendungen und von anderen Bibliotheken für NuGet-Abhängigkeiten verwendet.</span><span class="sxs-lookup"><span data-stu-id="aceb6-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="aceb6-110">Angenommen, Sie erstellen eine Anwendung und verwenden einen Open Source-Client zum Aufrufen eines Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="aceb6-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="aceb6-111">Sie können kein wichtiges Update für eine Abhängigkeit korrigieren, die der Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="aceb6-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="aceb6-112">Der Open Source-Client muss nämlich geändert werden, und das können Sie nicht steuern.</span><span class="sxs-lookup"><span data-stu-id="aceb6-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="aceb6-113">Sie müssen kompatible Bibliotheksversionen finden oder einen Fix an die Clientbibliothek übermitteln und auf eine neue Version warten.</span><span class="sxs-lookup"><span data-stu-id="aceb6-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="aceb6-114">Der schlimmste Fall ist, wenn Sie zwei Bibliotheken verwenden wollen, die von gegenseitig inkompatiblen Versionen einer dritten Bibliothek abhängen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

- <span data-ttu-id="aceb6-115">**Bibliotheken auf hoher Ebene** wie eine Sammlung von Steuerelementen der Benutzeroberfläche sind weniger anfällig für Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="aceb6-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="aceb6-116">Bibliotheken auf hoher Ebene werden direkt in einer Endbenutzeranwendung referenziert.</span><span class="sxs-lookup"><span data-stu-id="aceb6-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="aceb6-117">Wenn Breaking Changes auftreten, kann der Entwickler ein Update auf die neueste Version ausführen oder seine Anwendung ändern, um die Breaking Changes zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="aceb6-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="aceb6-118">✔️️ Überlegen Sie, wie Ihre Bibliothek verwendet werden wird.</span><span class="sxs-lookup"><span data-stu-id="aceb6-118">✔️ DO think about how your library will be used.</span></span> <span data-ttu-id="aceb6-119">Welche Auswirkungen haben Breaking Changes auf Anwendungen und Bibliotheken, die diese verwenden?</span><span class="sxs-lookup"><span data-stu-id="aceb6-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="aceb6-120">✔️ Minimieren Sie Breaking Changes beim Entwickeln einer .NET-Bibliothek auf niedriger Ebene.</span><span class="sxs-lookup"><span data-stu-id="aceb6-120">✔️ DO minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="aceb6-121">✔️ Veröffentlichen Sie eine in großen Teilen umgeschriebene Bibliothek gegebenenfalls als neues NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="aceb6-121">✔️ CONSIDER publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="aceb6-122">Arten von Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="aceb6-122">Types of breaking changes</span></span>

<span data-ttu-id="aceb6-123">Breaking Changes lassen sich in unterschiedliche Kategorien unterteilen und sind nicht gleichermaßen wirkungsvoll.</span><span class="sxs-lookup"><span data-stu-id="aceb6-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="aceb6-124">Breaking Changes in der Quelle</span><span class="sxs-lookup"><span data-stu-id="aceb6-124">Source breaking change</span></span>

<span data-ttu-id="aceb6-125">Breaking Changes in der Quelle wirken sich nicht auf die Programmausführung aus, verursachen allerdings Kompilierungsfehler, wenn die Anwendung das nächste Mal erneut kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="aceb6-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="aceb6-126">Beispielsweise kann eine neue Überladung eine Mehrdeutigkeit bei Methodenaufrufen erzeugen, die zuvor eindeutig waren, oder aber ein umbenannter Parameter unterbricht Aufrufer, die benannte Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="aceb6-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="aceb6-127">Da Breaking Changes in der Quelle nur dann schädlich sind, wenn Entwickler ihre Anwendungen erneut kompilieren, handelt es sich dabei um die harmlosesten Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="aceb6-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="aceb6-128">Entwickler können ihren eigenen fehlerhaften Quellcode einfach reparieren.</span><span class="sxs-lookup"><span data-stu-id="aceb6-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="aceb6-129">Behavior Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="aceb6-129">Behavior breaking change</span></span>

<span data-ttu-id="aceb6-130">Änderungen am Verhalten sind die häufigste Art von Breaking Changes: Fast jeder Behavior Change wirkt sich negativ auf die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="aceb6-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="aceb6-131">Änderungen an Ihrer Bibliothek, z.B. Methodensignaturen, ausgelöste Ausnahmen oder Ein- bzw. Ausgabedatenformaten, können sich negativ auf Ihre Bibliotheksnutzer auswirken.</span><span class="sxs-lookup"><span data-stu-id="aceb6-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="aceb6-132">Sogar eine Fehlerbehebung kann ein Breaking Change sein, wenn sich Benutzer auf das ehemals fehlerhafte Verhalten verlassen haben.</span><span class="sxs-lookup"><span data-stu-id="aceb6-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="aceb6-133">Das Hinzufügen von Funktionen und Verbessern von schlechtem Verhalten wird empfohlen. Wenn diese Vorgänge jedoch nicht richtig ausgeführt werden, können vorhandene Benutzer Schwierigkeiten mit Upgrades haben.</span><span class="sxs-lookup"><span data-stu-id="aceb6-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="aceb6-134">Ein Entwickler unterstützender Ansatz beim Umgang mit Behavior Breaking Changes besteht darin, sie hinter Einstellungen zu verstecken.</span><span class="sxs-lookup"><span data-stu-id="aceb6-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="aceb6-135">Mithilfe von Einstellungen können Entwickler auf die neueste Version Ihrer Bibliothek aktualisieren und dabei entscheiden, ob sie Änderungen vornehmen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="aceb6-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="aceb6-136">Diese Strategie ermöglicht es Entwicklern, auf dem neuesten Stand zu bleiben und zugleich ihren genutzten Code mit der Zeit anzupassen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="aceb6-137">So umfasst ASP.NET Core MVC beispielsweise das Konzept einer [Kompatibilitätsversion](/aspnet/core/mvc/compatibility-version), die die unter `MvcOptions` aktivierten und deaktivierten Funktionen ändert.</span><span class="sxs-lookup"><span data-stu-id="aceb6-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="aceb6-138">✔️ Deaktivieren Sie neue Features gegebenenfalls standardmäßig, wenn sie vorhandene Benutzer beeinträchtigen. Geben Sie Entwicklern die Möglichkeit, diese Features mit einer Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="aceb6-138">✔️ CONSIDER leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="aceb6-139">Binäre Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="aceb6-139">Binary breaking change</span></span>

<span data-ttu-id="aceb6-140">Ein binärer Breaking Change tritt auf, wenn Sie die öffentliche API Ihrer Bibliothek ändern, sodass Assemblys, die mit älteren Versionen Ihrer Bibliothek kompiliert wurden, die API nicht mehr aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="aceb6-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="aceb6-141">Wenn Sie beispielsweise die Signatur einer Methode durch Hinzufügen eines neuen Parameters ändern, werden Assemblys, die mit einer älteren Bibliotheksversion kompiliert wurden, ein <xref:System.MissingMethodException>-Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="aceb6-142">Eine binärer Breaking Change kann auch eine **ganze Assembly** unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="aceb6-143">Das Umbenennen einer Assembly mit `AssemblyName` ändert die Identität der Assembly ebenso wie das Hinzufügen, Entfernen oder Ändern des starken Namensschlüssels der Assembly.</span><span class="sxs-lookup"><span data-stu-id="aceb6-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="aceb6-144">Eine Änderung der Identität einer Assembly unterbricht alle kompilierten Codes, die diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="aceb6-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="aceb6-145">❌ Ändern Sie keine Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-145">❌ DO NOT change an assembly name.</span></span>

<span data-ttu-id="aceb6-146">❌ Den Schlüssel für die eindeutige Benennung weder hinzufügen, noch ändern oder entfernen</span><span class="sxs-lookup"><span data-stu-id="aceb6-146">❌ DO NOT add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="aceb6-147">✔️ Verwenden Sie abstrakte Basisklassen anstelle von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-147">✔️ CONSIDER using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="aceb6-148">Wenn Sie einer Schnittstelle etwas hinzufügen, tritt ein Fehler für vorhandene Typen auf, die diese implementieren.</span><span class="sxs-lookup"><span data-stu-id="aceb6-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="aceb6-149">Mit einer abstrakten Basisklasse können Sie eine standardmäßige virtuelle Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aceb6-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="aceb6-150">✔️ Platzieren Sie auf Typen und Membern, die Sie entfernen möchten, gegebenenfalls das <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="aceb6-150">✔️ CONSIDER placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="aceb6-151">Das Attribut muss Anweisungen zum Aktualisieren des Codes enthalten, damit die veraltete API nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aceb6-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="aceb6-152">Code, der Typen und Methoden mit <xref:System.ObsoleteAttribute> aufruft, generiert eine Buildwarnung mit der Meldung, die an das Attribut übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="aceb6-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="aceb6-153">Warnungen geben Personen, die die veraltete API verwenden, Zeit zum Migrieren, sodass die meisten Benutzer, wenn die veraltete API entfernt wird, diese nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="aceb6-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

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

<span data-ttu-id="aceb6-154">✔️ Behalten Sie Typen und Methoden mit <xref:System.ObsoleteAttribute> auf unbestimmte Zeit in Bibliotheken auf niedriger und mittlerer Ebene bei.</span><span class="sxs-lookup"><span data-stu-id="aceb6-154">✔️ CONSIDER keeping types and methods with the <xref:System.ObsoleteAttribute> indefinitely in low and middle-level libraries.</span></span>

> <span data-ttu-id="aceb6-155">Das Entfernen von APIs ist eine binärer Breaking Change.</span><span class="sxs-lookup"><span data-stu-id="aceb6-155">Removing APIs is a binary breaking change.</span></span> <span data-ttu-id="aceb6-156">Erwägen Sie, veraltete Typen und Methoden beizubehalten, falls ihre Verwaltung keinen kostspieligen und großen technischen Aufwand für die Bibliothek bedeutet.</span><span class="sxs-lookup"><span data-stu-id="aceb6-156">Considering keeping obsolete types and methods if maintaining them is low cost and doesn't add lot of technical debt to your library.</span></span> <span data-ttu-id="aceb6-157">Wenn Sie Typen und Methoden nicht entfernen, können Sie so die obigen Worst-Case-Szenarios vermeiden.</span><span class="sxs-lookup"><span data-stu-id="aceb6-157">Not removing types and methods can help avoid the worst-case scenarios mentioned above.</span></span>

## <a name="see-also"></a><span data-ttu-id="aceb6-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aceb6-158">See also</span></span>

- [<span data-ttu-id="aceb6-159">Versions- und Updateüberlegungen für C#-Entwickler</span><span class="sxs-lookup"><span data-stu-id="aceb6-159">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
- [<span data-ttu-id="aceb6-160">Umfassendes Handbuch für API-Breaking Changes in .NET</span><span class="sxs-lookup"><span data-stu-id="aceb6-160">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
- [<span data-ttu-id="aceb6-161">Regeln von Breaking Changes in .NET</span><span class="sxs-lookup"><span data-stu-id="aceb6-161">.NET breaking change rules</span></span>](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="aceb6-162">Vorherige</span><span class="sxs-lookup"><span data-stu-id="aceb6-162">Previous</span></span>](versioning.md)
