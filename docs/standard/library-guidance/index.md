---
title: Leitfaden zur Open Source-Bibliothek für .NET
description: Empfehlungen für bewährte Methoden für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken
author: jamesnk
ms.author: mairaw
ms.date: 10/17/2018
ms.openlocfilehash: a656094066eb43ffe64ab405784f4577621b5c46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910129"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="c3854-103">Leitfaden für die Open Source-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="c3854-103">Open-source library guidance</span></span>

<span data-ttu-id="c3854-104">Dieser Leitfaden bietet Empfehlungen für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="c3854-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="c3854-105">In dieser Dokumentation liegt der Fokus auf dem *Was* und *Warum* beim Erstellen einer .NET-Bibliothek und nicht auf dem *Wie*.</span><span class="sxs-lookup"><span data-stu-id="c3854-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="c3854-106">Aspekte hochqualitativer Open Source-Bibliotheken für .NET:</span><span class="sxs-lookup"><span data-stu-id="c3854-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="c3854-107">**Inklusiv:** Gute .NET-Bibliotheken sind dafür ausgelegt, viele Plattformen, Programmiersprachen und Anwendungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c3854-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="c3854-108">**Stabil:** Gute .NET-Bibliotheken existieren im .NET-Ökosystem nebeneinander und werden in Anwendungen ausgeführt, die mit vielen Bibliotheken erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c3854-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="c3854-109">**Für die Weiterentwickelung entworfen:** .NET-Bibliotheken sollten sich im Laufe der Zeit verbessern und weiterentwickeln, während Sie vorhandene Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c3854-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="c3854-110">**Debugfähig:** .NET-Bibliotheken sollten die neuesten Tools verwenden, um für Benutzer eine gute Debugleistung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c3854-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="c3854-111">**Vertrauenswürdig:** Entwickler haben Vertrauen zu .NET-Bibliotheken, da diese mithilfe bewährter Sicherheitsmethoden Inhalte auf NuGet veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c3854-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c3854-112">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="c3854-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="c3854-113">Empfehlungstypen</span><span class="sxs-lookup"><span data-stu-id="c3854-113">Types of recommendations</span></span>

<span data-ttu-id="c3854-114">Jeder Artikel enthält vier Empfehlungstypen: **Do**, **Erwägen**, **Vermeiden** und **Don‘t**.</span><span class="sxs-lookup"><span data-stu-id="c3854-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="c3854-115">Der Empfehlungstyp kennzeichnet, wie streng die Empfehlung befolgt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="c3854-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="c3854-116">Eine **Do**-Empfehlung sollten Sie fast immer befolgen.</span><span class="sxs-lookup"><span data-stu-id="c3854-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="c3854-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c3854-117">For example:</span></span>

<span data-ttu-id="c3854-118">**✔️ DO** Verteilen Sie Ihre Bibliothek mithilfe eines NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="c3854-118">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="c3854-119">Andererseits gibt es Empfehlungen, die Sie **erwägen** sollten. Berechtigte Ausnahmen bestätigen jedoch die Regel, und es ist auch nicht weiter schlimm, wenn Sie die folgende Anweisung nicht befolgen:</span><span class="sxs-lookup"><span data-stu-id="c3854-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="c3854-120">**✔️ ERWÄGEN** Sie, [SemVer 2.0.0](https://semver.org/) für die Versionskontrolle Ihres NuGet-Pakets zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3854-120">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="c3854-121">Empfehlungen hinsichtlich **Vermeiden** geben Dinge an, die allgemein als keine gute Idee angesehen werden, jedoch kann das Brechen dieser Regel manchmal auch sinnvoll sein:</span><span class="sxs-lookup"><span data-stu-id="c3854-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="c3854-122">**❌ VERMEIDEN** Sie NuGet-Paketverweise, die eine exakte Version erfordern.</span><span class="sxs-lookup"><span data-stu-id="c3854-122">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="c3854-123">Schließlich kennzeichnen **Do not**-Empfehlungen Vorgänge, die Sie niemals ausführen sollten:</span><span class="sxs-lookup"><span data-stu-id="c3854-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="c3854-124">**❌ DON‘T** Veröffentlichen Sie keine Versionen mit starkem Namen oder nicht starkem Namen Ihrer Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="c3854-124">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="c3854-125">Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="c3854-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="c3854-126">Nächste</span><span class="sxs-lookup"><span data-stu-id="c3854-126">Next</span></span>](get-started.md)