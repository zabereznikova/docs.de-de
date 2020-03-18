---
title: Versions- und Updateüberlegungen für C#-Entwickler
description: Die Einführung neuer Sprachfeatures in Ihrer Bibliothek kann sich auf den Code auswirken, der sie verwendet.
ms.date: 09/19/2018
ms.openlocfilehash: 3ffe2f6fd64a391fddf28233dccb022c95851884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398148"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="44344-103">Versions- und Updateüberlegungen für C#-Entwickler</span><span class="sxs-lookup"><span data-stu-id="44344-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="44344-104">Kompatibilität ist ein sehr wichtiges Ziel, wenn der Sprache C# neue Features hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="44344-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="44344-105">In nahezu allen Fällen kann vorhandener Code problemlos mit einer neuen Compilerversion neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="44344-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="44344-106">Möglicherweise ist mehr Sorgfalt erforderlich, wenn Sie neue Sprachfeatures in einer Bibliothek übernehmen.</span><span class="sxs-lookup"><span data-stu-id="44344-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="44344-107">Sie erstellen möglicherweise eine neue Bibliothek mit Features, die sich in der neuesten Version befinden, und müssen sicherstellen, dass Apps, die mit früheren Versionen des Compilers erstellt wurden, diese verwenden können.</span><span class="sxs-lookup"><span data-stu-id="44344-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="44344-108">Oder Sie nehmen ein Upgrade einer vorhandenen Bibliothek vor, und viele Ihrer Benutzer verfügen möglicherweise noch nicht über Versionen mit dem Upgrade.</span><span class="sxs-lookup"><span data-stu-id="44344-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="44344-109">Beim Treffen von Entscheidungen zur Übernahme neuer Features müssen Sie zwei Varianten von Kompatibilität unterscheiden: quellkompatibel und binärkompatibel.</span><span class="sxs-lookup"><span data-stu-id="44344-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="44344-110">Binärkompatible Änderungen</span><span class="sxs-lookup"><span data-stu-id="44344-110">Binary compatible changes</span></span>

<span data-ttu-id="44344-111">Änderungen an ihrer Bibliothek sind **binärkompatibel**, wenn Ihre aktualisierte Bibliothek ohne Neuerstellung der Anwendungen und Bibliotheken, die sie nutzen, verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="44344-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="44344-112">Abhängige Assemblys müssen nicht neu erstellt werden, und es sind keine Änderungen am Quellcode erforderlich.</span><span class="sxs-lookup"><span data-stu-id="44344-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="44344-113">Binärkompatible Änderungen sind zugleich auch quellkompatible Änderungen.</span><span class="sxs-lookup"><span data-stu-id="44344-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="44344-114">Quellkompatible Änderungen</span><span class="sxs-lookup"><span data-stu-id="44344-114">Source compatible changes</span></span>

<span data-ttu-id="44344-115">Änderungen an Ihrer Bibliothek sind **quellkompatibel**, wenn die Anwendungen und Bibliotheken, die Ihre Bibliothek nutzen, keine Änderungen am Quellcode erfordern, die Quellen aber mit der neuen Version neu kompiliert werden müssen, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="44344-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="44344-116">Inkompatible Änderungen</span><span class="sxs-lookup"><span data-stu-id="44344-116">Incompatible changes</span></span>

<span data-ttu-id="44344-117">Wenn eine Änderung weder **quellkompatibel** noch **binärkompatibel** ist, sind Änderungen am Quellcode in Kombination mit einer erneuten Kompilierung in den abhängigen Bibliotheken und Anwendungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="44344-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="44344-118">Bewerten Ihrer Bibliothek</span><span class="sxs-lookup"><span data-stu-id="44344-118">Evaluate your library</span></span>

<span data-ttu-id="44344-119">Diese Kompatibilitätskonzepte betreffen die öffentlichen und geschützten Deklarationen für Ihre Bibliothek, nicht deren interne Implementierung.</span><span class="sxs-lookup"><span data-stu-id="44344-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="44344-120">Die interne Übernahme beliebiger neuer Features ist immer **binärkompatibel**.</span><span class="sxs-lookup"><span data-stu-id="44344-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="44344-121">Bei **binärkompatiblen** Änderungen steht neue Syntax zur Verfügung, die den gleichen kompilierten Code für öffentliche Deklarationen erzeugt wie die ältere Syntax.</span><span class="sxs-lookup"><span data-stu-id="44344-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="44344-122">Beispielsweise ist das Ändern einer Methode in ein Ausdruckskörpermember eine **binärkompatible** Änderung:</span><span class="sxs-lookup"><span data-stu-id="44344-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="44344-123">Ursprünglicher Code:</span><span class="sxs-lookup"><span data-stu-id="44344-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="44344-124">Neuer Code:</span><span class="sxs-lookup"><span data-stu-id="44344-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="44344-125">Mit **quellkompatiblen** Änderungen wird Syntax eingeführt, die den kompilierten Code für ein öffentliches Member ändert, aber in einer Weise, die mit vorhandenen Aufrufsites kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="44344-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="44344-126">Beispielsweise ist das Ändern einer Methodensignatur von einem Wertparameter in einen `in`-Verweisparameter quellkompatibel, aber nicht binärkompatibel:</span><span class="sxs-lookup"><span data-stu-id="44344-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="44344-127">Ursprünglicher Code:</span><span class="sxs-lookup"><span data-stu-id="44344-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="44344-128">Neuer Code:</span><span class="sxs-lookup"><span data-stu-id="44344-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="44344-129">In den [Neuigkeiten](index.md)-Artikeln ist vermerkt, ob die Einführung eines Features, das sich auf öffentliche Deklarationen auswirkt, quellkompatibel oder binärkompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="44344-129">The [What's new](index.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>
