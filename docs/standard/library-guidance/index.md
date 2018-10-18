---
title: Leitfaden für die Open Source-Bibliothek
description: Empfehlungen für bewährte Methoden für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 50fb745f7eb65abcaca76cebaf9991c48f559e59
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374900"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="5689d-103">Leitfaden für die Open Source-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="5689d-103">Open-source library guidance</span></span>

<span data-ttu-id="5689d-104">Dieser Leitfaden bietet Empfehlungen für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="5689d-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="5689d-105">In dieser Dokumentation liegt der Fokus auf dem *Was* und *Warum* beim Erstellen einer .NET-Bibliothek und nicht auf dem *Wie*.</span><span class="sxs-lookup"><span data-stu-id="5689d-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="5689d-106">Aspekte hochqualitativer Open Source-Bibliotheken für .NET:</span><span class="sxs-lookup"><span data-stu-id="5689d-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5689d-107">**Inklusiv:** Gute .NET-Bibliotheken sind dafür ausgelegt, viele Plattformen und Anwendungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5689d-107">**Inclusive** - Good .NET libraries strive to support many platforms and applications.</span></span>
> * <span data-ttu-id="5689d-108">**Stabil:** Gute .NET-Bibliotheken existieren im .NET-Ökosystem nebeneinander und werden in Anwendungen ausgeführt, die mit vielen Bibliotheken erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5689d-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="5689d-109">**Für die Weiterentwickelung entworfen:** .NET-Bibliotheken sollten sich im Laufe der Zeit verbessern und weiterentwickeln, während Sie vorhandene Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5689d-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="5689d-110">**Debugfähig:** .NET-Bibliotheken sollten die neuesten Tools verwenden, um für Benutzer eine gute Debugleistung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5689d-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="5689d-111">**Vertrauenswürdig:** Entwickler haben Vertrauen zu .NET-Bibliotheken, da diese mithilfe bewährter Sicherheitsmethoden Inhalte auf NuGet veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="5689d-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5689d-112">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="5689d-112">Get Started</span></span>](./get-started.md)

## <a name="recommendations"></a><span data-ttu-id="5689d-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="5689d-113">Recommendations</span></span>

<span data-ttu-id="5689d-114">Mit jedem Artikel wird eine Liste der Empfehlungen für Ihre .NET-Bibliothek mit Aktionen veröffentlicht, die Sie **tun**, **erwägen**, **vermeiden** und **keinesfalls tun** sollten.</span><span class="sxs-lookup"><span data-stu-id="5689d-114">With each article, there is a list of recommendations for your .NET library using **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="5689d-115">Der Wortlaut jeder Empfehlung lässt darauf schließen, wie streng diese befolgt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="5689d-115">The wording of each recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="5689d-116">Eine **DO**-Empfehlung sollten Sie so gut wie immer befolgen:</span><span class="sxs-lookup"><span data-stu-id="5689d-116">A **Do** recommendation is one that should almost always be followed:</span></span>

<span data-ttu-id="5689d-117">**✔️ DO** Verteilen Sie Ihre Bibliothek mithilfe eines NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="5689d-117">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="5689d-118">Andererseits gibt es Empfehlungen, die Sie **erwägen** sollten. Berechtigte Ausnahmen bestätigen jedoch die Regel, und es ist auch nicht weiter schlimm, wenn Sie die folgende Anweisung nicht befolgen:</span><span class="sxs-lookup"><span data-stu-id="5689d-118">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="5689d-119">**✔️ ERWÄGEN** Sie, [SemVer 2.0.0](https://semver.org/) für die Versionskontrolle Ihres NuGet-Pakets zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5689d-119">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="5689d-120">Empfehlungen zur **Vermeidung** stehen für Dinge, die allgemein als keine gute Idee angesehen werden, jedoch kann das Brechen dieser Regel manchmal auch sinnvoll sein:</span><span class="sxs-lookup"><span data-stu-id="5689d-120">**Avoid** recommendations are things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="5689d-121">**❌ VERMEIDEN** Sie NuGet-Paketverweise, die eine exakte Version erfordern.</span><span class="sxs-lookup"><span data-stu-id="5689d-121">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="5689d-122">Schließlich gibt es noch Dinge, die Sie **keinesfalls tun sollten**:</span><span class="sxs-lookup"><span data-stu-id="5689d-122">And finally, **do not** indicates something you should almost never do:</span></span>

<span data-ttu-id="5689d-123">**❌ DON‘T** Veröffentlichen Sie keine Versionen mit starkem Namen oder nicht starkem Namen Ihrer Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="5689d-123">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="5689d-124">Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="5689d-124">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="5689d-125">Nächste</span><span class="sxs-lookup"><span data-stu-id="5689d-125">Next</span></span>](./get-started.md)
