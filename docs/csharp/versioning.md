---
title: Versionierung in C# – Leitfaden für C#
description: Informationen zur Versionierung in C# und .NET
ms.date: 01/08/2017
ms.technology: csharp-advanced-concepts
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: 124cce51865f04a555bc121fb6ce18cc95591bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156466"
---
# <a name="versioning-in-c"></a><span data-ttu-id="ab1aa-103">Versionierung in C\#</span><span class="sxs-lookup"><span data-stu-id="ab1aa-103">Versioning in C\#</span></span>

<span data-ttu-id="ab1aa-104">In diesem Tutorial erfahren Sie, welche Rolle die Versionierung in .NET spielt.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-104">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="ab1aa-105">Außerdem erfahren Sie, welche Faktoren Sie berücksichtigen müssen, wenn Sie Ihre Bibliothek versionieren oder ein Upgrade auf eine neue Version einer Bibliothek durchführen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-105">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="ab1aa-106">Erstellen von Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ab1aa-106">Authoring Libraries</span></span>

<span data-ttu-id="ab1aa-107">Als Entwickler, der bereits .NET-Bibliotheken für die öffentliche Verwendung erstellt hat, waren Sie bestimmt schon in Situationen, in denen Sie neue Updates implementieren mussten.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-107">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="ab1aa-108">Die richtige Vorgehensweise ist hier sehr wichtig, da Sie sicherstellen müssen, dass es einen nahtlosen Übergang von vorhandenem Code auf die neue Version Ihrer Bibliothek gibt.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-108">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="ab1aa-109">Folgendes Punkte spielen eine Rolle, wenn Sie eine neue Version erstellen:</span><span class="sxs-lookup"><span data-stu-id="ab1aa-109">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="ab1aa-110">Semantische Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="ab1aa-110">Semantic Versioning</span></span>

<span data-ttu-id="ab1aa-111">[Semantic versioning](https://semver.org/) (Semantische Versionierung, kurz SemVer) ist eine Namenskonvention, die auf Versionen Ihrer Bibliothek angewendet wird, um bestimmte Meilensteinereignisse zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-111">[Semantic versioning](https://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="ab1aa-112">Im Idealfall sollten es die Versionsinformationen Ihrer Bibliothek Entwicklern erleichtern, festzustellen, ob ihre Projekte, die ältere Versionen dieser Bibliothek verwenden, kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-112">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="ab1aa-113">Die einfachste Herangehensweise an SemVer ist das Format `MAJOR.MINOR.PATCH` mit drei Komponenten, bei dem:</span><span class="sxs-lookup"><span data-stu-id="ab1aa-113">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>

- <span data-ttu-id="ab1aa-114">`MAJOR` inkrementiert wird, wenn Sie nicht kompatible API-Änderungen durchführen</span><span class="sxs-lookup"><span data-stu-id="ab1aa-114">`MAJOR` is incremented when you make incompatible API changes</span></span>
- <span data-ttu-id="ab1aa-115">`MINOR` inkrementiert wird, wenn Sie abwärtskompatible Funktionalität hinzufügen</span><span class="sxs-lookup"><span data-stu-id="ab1aa-115">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
- <span data-ttu-id="ab1aa-116">`PATCH` inkrementiert wird, wenn Sie abwärtskompatible Fehlerkorrekturen durchführen</span><span class="sxs-lookup"><span data-stu-id="ab1aa-116">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="ab1aa-117">Es besteht auch die Möglichkeit, andere Szenarios wie Vorabversionen usw. anzugeben, wenn Sie die Versionsinformationen auf Ihre .NET-Bibliothek anwenden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-117">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="ab1aa-118">Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="ab1aa-118">Backwards Compatibility</span></span>

<span data-ttu-id="ab1aa-119">Die Abwärtskompatibilität mit früheren Versionen ist wahrscheinlich eine Ihrer Hauptsorgen, wenn Sie neue Versionen Ihrer Bibliothek veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-119">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="ab1aa-120">Bei einer neuen Version Ihrer Bibliothek besteht Quellenkompatibilität mit einer früheren Version, wenn Code, der von früheren Versionen abhängt, durch erneutes Kompilieren mit der neuen Version funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-120">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span>
<span data-ttu-id="ab1aa-121">Bei einer neuen Version Ihrer Bibliothek besteht binäre Kompatibilität, wenn eine Anwendung, die von der alten Versionen abhängt, ohne erneutes Kompilieren mit der neuen Version arbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-121">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="ab1aa-122">Folgende Punkte sollten Sie beachten, wenn Sie versuchen die Abwärtskompatibilität mit älteren Versionen ihrer Bibliothek aufrechtzuerhalten:</span><span class="sxs-lookup"><span data-stu-id="ab1aa-122">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

- <span data-ttu-id="ab1aa-123">Virtuelle Methoden: Wenn Sie eine virtuelle Methode in Ihrer neuen Version in eine nicht-virtuelle Methode umwandeln, bedeutet das, dass die Projekte, die diese Methode außer Kraft setzen, aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-123">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="ab1aa-124">Es handelt sich um eine schwere grundlegende Änderung, von der stark abgeraten wird.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-124">This is a huge breaking change and is strongly discouraged.</span></span>
- <span data-ttu-id="ab1aa-125">Methodensignaturen: Wenn Sie beim Aktualisieren des Verhaltens einer Methode ebenfalls deren Signatur ändern müssen, sollten Sie stattdessen eine Überladung erstellen, damit der Code, der diese Methode aufruft, weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-125">Method signatures: When updating a method behavior requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="ab1aa-126">Sie können die alte Methodensignatur immer so ändern, dass sie die neue Methodensignatur aufruft. Dadurch bleibt die Implementierung konsistent.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-126">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
- <span data-ttu-id="ab1aa-127">[Obsolete-Attribut](programming-guide/concepts/attributes/common-attributes.md#Obsolete): Sie können dieses Attribut in Ihrem Code verwenden, um Klassen oder Klassenmember anzugeben, die veraltet sind und in zukünftigen Versionen vermutlich gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-127">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span> <span data-ttu-id="ab1aa-128">Dadurch sind Entwickler, die Ihre Bibliothek verwenden, besser auf grundlegende Änderungen vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-128">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
- <span data-ttu-id="ab1aa-129">Optionale Methodenargumente: Wenn sie vorher optionale in obligatorische Methodenargumente umwandeln oder ihren Standardwert ändern, muss der gesamte Code, der diese Argumente nicht bereitstellt, aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-129">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>

> [!NOTE]
> <span data-ttu-id="ab1aa-130">Die Umwandlung von obligatorischen Argumenten in optionale sollte nur geringe Auswirkungen haben, besonders, wenn dadurch das Verhalten der Methode nicht geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-130">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behavior.</span></span>

<span data-ttu-id="ab1aa-131">Je leichter Sie es Ihren Benutzern machen, auf die neue Version Ihrer Bibliothek zu aktualisieren, desto früher werden sie dieses Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-131">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="ab1aa-132">Anwendungskonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ab1aa-132">Application Configuration File</span></span>

<span data-ttu-id="ab1aa-133">Als .NET-Entwickler haben Sie sehr wahrscheinlich schon einmal mit [der `app.config`-Datei](../framework/configure-apps/file-schema/index.md) gearbeitet, die in den meisten Projekttypen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-133">As a .NET developer there's a very high chance you've encountered [the `app.config` file](../framework/configure-apps/file-schema/index.md) present in most project types.</span></span>
<span data-ttu-id="ab1aa-134">Diese einfache Konfigurationsdatei kann beim Verbessern der Einführung neuer Updates einen großen Unterschied machen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-134">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="ab1aa-135">In der Regel sollten Sie Ihre Bibliotheken so anlegen, dass die Informationen, die sich wahrscheinlich häufiger ändern, in der Datei `app.config` gespeichert werden. Auf diese Weise muss die Konfigurationsdatei früherer Versionen nur durch die neue Datei ersetzt werden, wenn solche Informationen aktualisiert werden. Eine erneute Kompilierung der Bibliothek ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-135">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated, the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="ab1aa-136">Verarbeiten von Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ab1aa-136">Consuming Libraries</span></span>

<span data-ttu-id="ab1aa-137">Als Entwickler, der .NET-Bibliotheken verarbeitet, die von anderen Entwicklern erstellt wurden, sind Sie sich sicher der Tatsache bewusst, dass eine neue Version einer Bibliothek möglicherweise nicht voll kompatibel mit Ihrem Projekt ist, und Sie Ihren Code oft aktualisieren müssen, um auf diese Änderungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-137">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="ab1aa-138">Glücklicherweise gibt es in C#-und dem .NET-Ökosystem Features und Techniken, mit denen Sie Apps leicht aktualisieren können, damit sie mit neuen Versionen von Bibliotheken funktionieren, mit denen möglicherweise Breaking Changes eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-138">Lucky for you, C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="ab1aa-139">Assemblybindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="ab1aa-139">Assembly Binding Redirection</span></span>

<span data-ttu-id="ab1aa-140">Sie können die Datei *app.config* zum Aktualisieren der Version einer von Ihrer App verwendeten Bibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-140">You can use the *app.config* file to update the version of a library your app uses.</span></span> <span data-ttu-id="ab1aa-141">Durch Hinzufügen einer sogenannten [*Bindungsumleitung*](../framework/configure-apps/redirect-assembly-versions.md) können Sie die neue Version der Bibliothek verwenden, ohne dass Sie Ihre App erneut kompilieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-141">By adding what is called a [*binding redirect*](../framework/configure-apps/redirect-assembly-versions.md), you can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="ab1aa-142">Im folgenden Beispiel wird gezeigt, wie Sie die *app.config*-Datei Ihrer App aktualisieren, um die Patchversion `1.0.1` von `ReferencedLibrary` zu verwenden, statt der Version `1.0.0`, mit der sie ursprünglich kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-142">The following example shows how you would update your app's *app.config* file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="ab1aa-143">Dieser Ansatz funktioniert nur, wenn die neue Version von `ReferencedLibrary` binär kompatibel mit Ihrer Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-143">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="ab1aa-144">Im Abschnitt [Abwärtskompatibilität](#backwards-compatibility) finden Sie Änderungen, die Sie beachten müssen, wenn Sie die Kompatibilität bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-144">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="ab1aa-145">neu</span><span class="sxs-lookup"><span data-stu-id="ab1aa-145">new</span></span>

<span data-ttu-id="ab1aa-146">Sie können den `new`-Modifizierer verwenden, um geerbte Member einer Basisklasse auszublenden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-146">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="ab1aa-147">Dies ist eine Möglichkeit, wie abgeleitete Klassen auf Updates in Basisklassen reagieren können.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-147">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="ab1aa-148">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ab1aa-148">Take the following example:</span></span>

[!code-csharp[Sample usage of the 'new' modifier](~/samples/snippets/csharp/versioning/new/Program.cs#sample)]

<span data-ttu-id="ab1aa-149">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="ab1aa-149">**Output**</span></span>

```console
A base method
A derived method
```

<span data-ttu-id="ab1aa-150">Im obigen Beispiel können Sie sehen, wie `DerivedClass` die Methode `MyMethod` ausblendet, die sich in `BaseClass` befindet.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-150">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="ab1aa-151">Das bedeutet, dass Sie einfach den `new`-Modifizierer auf Ihre abgeleiteten Klassenmember anwenden können, um die Member der Basisklasse auszublenden, wenn von einer Basisklasse in der neuen Version einer Bibliothek Member hinzugefügt werden, die sich bereits in Ihrer abgeleiteten Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-151">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="ab1aa-152">Wenn kein `new`-Modifizierer angegeben ist, blendet eine abgeleitete Klasse standardmäßig in Konflikt stehende Member in der Basisklasse aus. Obwohl eine Compilerwarnung generiert wird, kompiliert der Code weiter.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-152">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="ab1aa-153">Das bedeutet, dass die neue Version Ihrer Bibliothek durch das Hinzufügen neuer Member zu einer vorhanden Klasse sowohl quellen- als auch binär kompatibel mit dem Code wird, der von ihr abhängt.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-153">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="ab1aa-154">override</span><span class="sxs-lookup"><span data-stu-id="ab1aa-154">override</span></span>

<span data-ttu-id="ab1aa-155">Der `override`-Modifizierer bedeutet, dass eine abgeleitete Implementierung die Implementierung eines Basisklassenmembers erweitert, anstatt sie auszublenden.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-155">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="ab1aa-156">Der `virtual`-Modifizierer muss auf den Basisklassenmember angewendet sein.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-156">The base class member needs to have the `virtual` modifier applied to it.</span></span>

[!code-csharp[Sample usage of the 'override' modifier](../../samples/snippets/csharp/versioning/override/Program.cs#sample)]

<span data-ttu-id="ab1aa-157">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="ab1aa-157">**Output**</span></span>

```console
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="ab1aa-158">Der `override`-Modifizierer wird beim Kompilieren ausgewertet, und der Compiler löst einen Fehler aus, wenn kein virtueller Member gefunden wird, der außer Kraft gesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-158">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="ab1aa-159">Ihre Kenntnis der besprochenen Techniken und Ihr Wissen, in welchen Situationen diese angewendet werden, wird wesentlich dazu beitragen, den Übergang zwischen den Versionen einer Bibliothek zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="ab1aa-159">Your knowledge of the discussed techniques and your understanding of the situations in which to use them, will go a long way towards easing the transition between versions of a library.</span></span>
