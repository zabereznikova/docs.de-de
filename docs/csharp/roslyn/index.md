---
title: "Verwenden des .NET Compiler SDK – Leitfaden für C#"
description: Erkunden Sie die Roslyn-APIs zum Erstellen automatischer Diagnosen und Codefehlerbehebungen.
keywords: .NET, .NET Core, C#, Roslyn,
ms.date: 06/25/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: abed9e00-2ddc-468e-9cca-d033bd6a7e36
redirect_url: /dotnet/csharp/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b227d67fd5431da328e1686fd9afc6a3b9db035e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="-using-the-net-compiler-sdk"></a><span data-ttu-id="66c4a-104">🔧 Verwenden des .NET Compiler SDK</span><span class="sxs-lookup"><span data-stu-id="66c4a-104">🔧 Using the .NET Compiler SDK</span></span>

> <span data-ttu-id="66c4a-105">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="66c4a-105">**Note**</span></span>
> 
> <span data-ttu-id="66c4a-106">Zu diesem Thema wurde noch nichts geschrieben.</span><span class="sxs-lookup"><span data-stu-id="66c4a-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="66c4a-107">Wir freuen uns auf Ihre Ideen zur Gestaltung des Umfangs und der Herangehensweise.</span><span class="sxs-lookup"><span data-stu-id="66c4a-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="66c4a-108">Sie können den Status nachverfolgen und Informationen zu diesem [Problem](https://github.com/dotnet/docs/issues/972) auf GitHub bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="66c4a-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/972) at GitHub.</span></span>
> 
> <span data-ttu-id="66c4a-109">Wenn Sie früher Entwürfe und Überblicke zu diesem Thema erhalten möchten, geben Sie Ihre Kontaktinformationen bei dem Thema an.</span><span class="sxs-lookup"><span data-stu-id="66c4a-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="66c4a-110">Erfahren Sie auf [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md) mehr darüber, wie Sie hierzu beitragen können.</span><span class="sxs-lookup"><span data-stu-id="66c4a-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

<span data-ttu-id="66c4a-111">Dies ist ein Metathema für einen ganzen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="66c4a-111">This is a meta-topic for an entire section.</span></span> <span data-ttu-id="66c4a-112">Folgende Bereiche sollten hier behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="66c4a-112">Areas that need to be covered here include:</span></span> 
* <span data-ttu-id="66c4a-113">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="66c4a-113">Getting Started</span></span>
* <span data-ttu-id="66c4a-114">Beispiele und Tutorials</span><span class="sxs-lookup"><span data-stu-id="66c4a-114">Samples and tutorials</span></span>
* <span data-ttu-id="66c4a-115">Konzeptionelle Inhalte</span><span class="sxs-lookup"><span data-stu-id="66c4a-115">conceptual content</span></span>
* <span data-ttu-id="66c4a-116">API-Gesamtmodell</span><span class="sxs-lookup"><span data-stu-id="66c4a-116">overall model of the APIs</span></span>
* <span data-ttu-id="66c4a-117">Link zu Beispielen zum [roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers)-Repository</span><span class="sxs-lookup"><span data-stu-id="66c4a-117">links to samples on the [roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers) repository</span></span>
* <span data-ttu-id="66c4a-118">Links zu anderen Referenzinhalten</span><span class="sxs-lookup"><span data-stu-id="66c4a-118">links to other reference content</span></span>

