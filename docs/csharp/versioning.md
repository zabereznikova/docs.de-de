---
title: "Versionierung in C# – Leitfaden für C#"
description: Informationen zur Versionierung in C# und .NET
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.date: 01/08/2017
ms.topic: article
ms.prod: visual-studio-dev-14
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: 0b671333019c00abafcfb72533e30936f8fc6ad7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="versioning-in-c"></a><span data-ttu-id="66646-104">Versionierung in C#</span><span class="sxs-lookup"><span data-stu-id="66646-104">Versioning in C#</span></span> #

<span data-ttu-id="66646-105">In diesem Tutorial erfahren Sie, welche Rolle die Versionierung in .NET spielt.</span><span class="sxs-lookup"><span data-stu-id="66646-105">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="66646-106">Außerdem erfahren Sie, welche Faktoren Sie berücksichtigen müssen, wenn Sie die Versionen Ihrer Bibliothek verwalten oder ein Upgrade auf eine neue Version der Bibliothek durchführen.</span><span class="sxs-lookup"><span data-stu-id="66646-106">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of the a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="66646-107">Erstellen von Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="66646-107">Authoring Libraries</span></span>

<span data-ttu-id="66646-108">Als Entwickler, der bereits .NET-Bibliotheken für die öffentliche Verwendung erstellt hat, waren Sie bestimmt schon in Situationen, in denen Sie neue Updates implementieren mussten.</span><span class="sxs-lookup"><span data-stu-id="66646-108">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="66646-109">Die richtige Vorgehensweise ist hier sehr wichtig, da Sie sicherstellen müssen, dass es einen nahtlosen Übergang von vorhandenem Code auf die neue Version Ihrer Bibliothek gibt.</span><span class="sxs-lookup"><span data-stu-id="66646-109">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="66646-110">Folgendes Punkte spielen eine Rolle, wenn Sie eine neue Version erstellen:</span><span class="sxs-lookup"><span data-stu-id="66646-110">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="66646-111">Semantische Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="66646-111">Semantic Versioning</span></span>

<span data-ttu-id="66646-112">[Semantic versioning](http://semver.org/) (Semantische Versionierung, kurz SemVer) ist eine Namenskonvention, die auf Versionen Ihrer Bibliothek angewendet wird, um bestimmte Meilensteinereignisse zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="66646-112">[Semantic versioning](http://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="66646-113">Im Idealfall sollten es die Versionsinformationen Ihrer Bibliothek Entwicklern erleichtern, festzustellen, ob ihre Projekte, die ältere Versionen dieser Bibliothek verwenden, kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="66646-113">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="66646-114">Die einfachste Herangehensweise an SemVer ist das Format `MAJOR.MINOR.PATCH` mit drei Komponenten, bei dem:</span><span class="sxs-lookup"><span data-stu-id="66646-114">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>
 
* <span data-ttu-id="66646-115">`MAJOR` inkrementiert wird, wenn Sie nicht kompatible API-Änderungen durchführen</span><span class="sxs-lookup"><span data-stu-id="66646-115">`MAJOR` is incremented when you make incompatible API changes</span></span>
* <span data-ttu-id="66646-116">`MINOR` inkrementiert wird, wenn Sie abwärtskompatible Funktionalität hinzufügen</span><span class="sxs-lookup"><span data-stu-id="66646-116">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
* <span data-ttu-id="66646-117">`PATCH` inkrementiert wird, wenn Sie abwärtskompatible Fehlerkorrekturen durchführen</span><span class="sxs-lookup"><span data-stu-id="66646-117">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="66646-118">Es besteht auch die Möglichkeit, andere Szenarios wie Vorabversionen usw. anzugeben, wenn Sie die Versionsinformationen auf Ihre .NET-Bibliothek anwenden.</span><span class="sxs-lookup"><span data-stu-id="66646-118">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="66646-119">Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="66646-119">Backwards Compatibility</span></span>

<span data-ttu-id="66646-120">Die Abwärtskompatibilität mit früheren Versionen ist wahrscheinlich eine Ihrer Hauptsorgen, wenn Sie neue Versionen Ihrer Bibliothek veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="66646-120">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="66646-121">Bei einer neuen Version Ihrer Bibliothek besteht Quellenkompatibilität mit einer früheren Version, wenn Code, der von früheren Versionen abhängt, durch erneutes Kompilieren mit der neuen Version funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="66646-121">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span> <span data-ttu-id="66646-122">Bei einer neuen Version Ihrer Bibliothek besteht binäre Kompatibilität, wenn eine Anwendung, die von der alten Versionen abhängt, ohne erneutes Kompilieren mit der neuen Version arbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="66646-122">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="66646-123">Folgende Punkte sollten Sie beachten, wenn Sie versuchen die Abwärtskompatibilität mit älteren Versionen ihrer Bibliothek aufrechtzuerhalten:</span><span class="sxs-lookup"><span data-stu-id="66646-123">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

* <span data-ttu-id="66646-124">Virtuelle Methoden: Wenn Sie eine virtuelle Methode in Ihrer neuen Version in eine nicht-virtuelle Methode umwandeln, bedeutet das, dass die Projekte, die diese Methode außer Kraft setzen, aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="66646-124">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="66646-125">Es handelt sich um eine schwere grundlegende Änderung, von der stark abgeraten wird.</span><span class="sxs-lookup"><span data-stu-id="66646-125">This is a huge breaking change and is strongly discouraged.</span></span>
* <span data-ttu-id="66646-126">Methodensignaturen: Wenn Sie beim Aktualisieren des Verhaltens einer Methode ebenfalls deren Signatur ändern müssen, sollten Sie stattdessen eine Überladung erstellen, damit der Code, der diese Methode aufruft, weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="66646-126">Method signatures: When updating a method behaviour requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="66646-127">Sie können die alte Methodensignatur immer so ändern, dass sie die neue Methodensignatur aufruft. Dadurch bleibt die Implementierung konsistent.</span><span class="sxs-lookup"><span data-stu-id="66646-127">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
* <span data-ttu-id="66646-128">[Obsolete attribute (Attribut „Obsolete“)](programming-guide/concepts/attributes/common-attributes.md#Obsolete): Sie können dieses Attribut in Ihrem Code verwenden, um Klassen oder Klassenmember anzugeben, die veraltet sind und in zukünftigen Versionen vermutlich gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="66646-128">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span>
<span data-ttu-id="66646-129">Dadurch sind Entwickler, die Ihre Bibliothek verwenden, besser auf grundlegende Änderungen vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="66646-129">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
* <span data-ttu-id="66646-130">Optionale Methodenargumente: Wenn sie vorher optionale in obligatorische Methodenargumente umwandeln oder ihren Standardwert ändern, muss der gesamte Code, der diese Argumente nicht bereitstellt, aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="66646-130">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>
> [!NOTE]
> <span data-ttu-id="66646-131">Obligatorische Argumente in optionale Argumente umzuwandeln, sollte nur geringe Auswirkungen haben, besonders, wenn dadurch das Verhalten der Methode nicht geändert wird.</span><span class="sxs-lookup"><span data-stu-id="66646-131">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behaviour.</span></span>

<span data-ttu-id="66646-132">Je leichter Sie es Ihren Benutzern machen, auf die neue Version Ihrer Bibliothek zu aktualisieren, desto früher werden sie dieses Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="66646-132">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="66646-133">Anwendungskonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="66646-133">Application Configuration File</span></span>

<span data-ttu-id="66646-134">Als .NET-Entwickler haben Sie sehr wahrscheinlich schon einmal mit [der `app.config`-Datei](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx) gearbeitet, die in den meisten Projekttypen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="66646-134">As a .NET developer there's a very high chance you've encountered [the `app.config` file](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx) present in most project types.</span></span>
<span data-ttu-id="66646-135">Diese einfache Konfigurationsdatei kann beim Verbessern der Einführung neuer Updates einen großen Unterschied machen.</span><span class="sxs-lookup"><span data-stu-id="66646-135">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="66646-136">In der Regel sollten Sie Ihre Bibliotheken so anlegen, dass die Informationen, die sich wahrscheinlich häufiger ändern, in der Datei `app.config` gespeichert werden. Daher muss die Konfigurationsdatei früherer Versionen nur mit der neuen Datei ersetzt werden, wenn solche Informationen aktualisiert werden. Die Bibliothek muss dann nicht mehr neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="66646-136">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="66646-137">Verarbeiten von Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="66646-137">Consuming Libraries</span></span>

<span data-ttu-id="66646-138">Als Entwickler, der .NET-Bibliotheken verarbeitet, die von anderen Entwicklern erstellt wurden, sind Sie sich sicher der Tatsache bewusst, dass eine neue Version einer Bibliothek möglicherweise nicht voll kompatibel mit Ihrem Projekt ist, und Sie Ihren Code oft aktualisieren müssen, um auf diese Änderungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="66646-138">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="66646-139">Zum Glück gibt es im C# -und .NET-Ökosystem Features und Techniken, mit denen Sie Anwendungen leicht aktualisieren können, damit sie mit neuen Versionen von Bibliotheken funktionieren, mit denen möglicherweise grundlegende Änderungen eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="66646-139">Lucky for you C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="66646-140">Assemblybindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="66646-140">Assembly Binding Redirection</span></span>

<span data-ttu-id="66646-141">Sie können die Datei `app.config` zum Aktualisieren der Version einer von Ihrer Anwendung verwendeten Bibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="66646-141">You can use the `app.config` file to update the version of a library your app uses.</span></span> <span data-ttu-id="66646-142">Durch Hinzufügen einer sogenannten [*binding redirect*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx) (Bindungsumleitung) können Sie die neue Version der Bibliothek verwenden, ohne dass Sie Ihre Anwendung erneut kompilieren müssen.</span><span class="sxs-lookup"><span data-stu-id="66646-142">By adding what is called a [*binding redirect*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx) your can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="66646-143">Im folgenden Beispiel wird gezeigt, wie Sie die Datei `app.config` Ihrer Anwendung aktualisieren, um die Patchversion `1.0.1` von `ReferencedLibrary` zu verwenden und nicht die Version `1.0.0`, mit der sie ursprünglich kompiliert war.</span><span class="sxs-lookup"><span data-stu-id="66646-143">The following example shows how you would update your app's `app.config` file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="66646-144">Dieser Ansatz funktioniert nur, wenn die neue Version von `ReferencedLibrary` binär kompatibel mit Ihrer Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="66646-144">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="66646-145">Im Abschnitt [Abwärtskompatibilität](#backwards-compatibility) finden Sie Änderungen, die Sie beachten müssen, wenn Sie die Kompatibilität bestimmen.</span><span class="sxs-lookup"><span data-stu-id="66646-145">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="66646-146">neu</span><span class="sxs-lookup"><span data-stu-id="66646-146">new</span></span>

<span data-ttu-id="66646-147">Sie können den `new`-Modifizierer verwenden, um geerbte Member einer Basisklasse auszublenden.</span><span class="sxs-lookup"><span data-stu-id="66646-147">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="66646-148">Dies ist eine Möglichkeit, wie abgeleitete Klassen auf Updates in Basisklassen reagieren können.</span><span class="sxs-lookup"><span data-stu-id="66646-148">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="66646-149">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="66646-149">Take the following example:</span></span>

[!code-csharp[Sample usage of the 'new' modifier](../../samples/csharp/versioning/new/Program.cs#sample)]

<span data-ttu-id="66646-150">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="66646-150">**Output**</span></span>

```
A base method
A derived method
```

<span data-ttu-id="66646-151">Im obigen Beispiel können Sie sehen, wie `DerivedClass` die Methode `MyMethod` ausblendet, die sich in `BaseClass` befindet.</span><span class="sxs-lookup"><span data-stu-id="66646-151">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="66646-152">Das bedeutet, dass Sie einfach den `new`-Modifizierer auf Ihre abgeleiteten Klassenmember anwenden können, um die Member der Basisklasse auszublenden, wenn von einer Basisklasse in der neuen Version einer Bibliothek Member hinzugefügt werden, die sich bereits in Ihrer abgeleiteten Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="66646-152">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="66646-153">Wenn kein `new`-Modifizierer angegeben ist, blendet eine abgeleitete Klasse standardmäßig in Konflikt stehende Member in der Basisklasse aus. Obwohl eine Compilerwarnung generiert wird, kompiliert der Code weiter.</span><span class="sxs-lookup"><span data-stu-id="66646-153">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="66646-154">Das bedeutet, dass die neue Version Ihrer Bibliothek durch das Hinzufügen neuer Member zu einer vorhanden Klasse sowohl quellen- als auch binär kompatibel mit dem Code wird, der von ihr abhängt.</span><span class="sxs-lookup"><span data-stu-id="66646-154">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="66646-155">override</span><span class="sxs-lookup"><span data-stu-id="66646-155">override</span></span>

<span data-ttu-id="66646-156">Der `override`-Modifizierer bedeutet, dass eine abgeleitete Implementierung die Implementierung eines Basisklassenmembers erweitert, anstatt sie auszublenden.</span><span class="sxs-lookup"><span data-stu-id="66646-156">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="66646-157">Der `virtual`-Modifizierer muss auf den Basisklassenmember angewendet sein.</span><span class="sxs-lookup"><span data-stu-id="66646-157">The base class member needs to have the `virtual` modifier applied to it.</span></span>

[!code-csharp[Sample usage of the 'override' modifier](../../samples/csharp/versioning/override/Program.cs#sample)]

<span data-ttu-id="66646-158">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="66646-158">**Output**</span></span>

```
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="66646-159">Der `override`-Modifizierer wird beim Kompilieren ausgewertet, und der Compiler löst einen Fehler aus, wenn kein virtueller Member gefunden wird, der außer Kraft gesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="66646-159">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="66646-160">Ihre Kenntnis der besprochenen Techniken und Ihr Wissen, in welchen Situationen diese angewendet werden, kann einen großen Unterschied beim reibungslosen Übergang zwischen den Versionen einer Bibliothek ausmachen.</span><span class="sxs-lookup"><span data-stu-id="66646-160">Your knowledge of the discussed techniques as well as your understanding of what situations to use them will go a long way to boost the ease of transition between versions of a library.</span></span>
