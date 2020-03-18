---
title: Erste Schritte beim Erstellen hochwertiger .NET-Bibliotheken
description: Erste Schritte beim Erstellen von .NET-Bibliotheken.
ms.date: 10/02/2018
ms.openlocfilehash: 10576219d8470a171ad0f1f347196999b2a2ee03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706490"
---
# <a name="get-started"></a><span data-ttu-id="4e43d-103">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="4e43d-103">Get started</span></span>

## <a name="cross-platform-targeting"></a>[<span data-ttu-id="4e43d-104">Plattformübergreifende Ziele</span><span class="sxs-lookup"><span data-stu-id="4e43d-104">Cross-platform targeting</span></span>](./cross-platform-targeting.md)

<span data-ttu-id="4e43d-105">Verwenden von .NET Standard und dem Festlegen von Zielversionen zum Erstellen plattformübergreifender Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="4e43d-105">How to use .NET Standard and multi-targeting to create cross-platform libraries.</span></span> <span data-ttu-id="4e43d-106">.NET läuft an vielen Stellen, und gute .NET-Bibliotheken sollten so viele Plattformen und Entwickler wie möglich unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4e43d-106">.NET runs in many places, and good .NET libraries should strive to support as many platforms and developers as possible.</span></span>

## <a name="strong-naming"></a>[<span data-ttu-id="4e43d-107">Starke Namen</span><span class="sxs-lookup"><span data-stu-id="4e43d-107">Strong naming</span></span>](./strong-naming.md)

<span data-ttu-id="4e43d-108">Erfahren Sie mehr zu den Vor- und Nachteilen eines starken Namens.</span><span class="sxs-lookup"><span data-stu-id="4e43d-108">Learn about strong naming and its advantages and disadvantages.</span></span> <span data-ttu-id="4e43d-109">Wenn für eine .NET-Bibliothek ein starker Name verwendet wird, kann diese von den meisten Entwicklern verwendet werden. Außerdem ist dies die empfohlene bewährte Methode.</span><span class="sxs-lookup"><span data-stu-id="4e43d-109">Strong naming a .NET library allows the most developers to use it and is a recommended best practice.</span></span>

## <a name="nuget-and-open-source-libraries"></a>[<span data-ttu-id="4e43d-110">NuGet und Open-Source-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="4e43d-110">NuGet and open-source libraries</span></span>](./nuget.md)

<span data-ttu-id="4e43d-111">Der beste Weg, NuGet-Pakete für Open-Source-.NET-Bibliotheken zu erstellen, einschließlich empfohlener Metadaten für alle Pakete, die öffentlich auf NuGet.org veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="4e43d-111">The best way to create NuGet packages for open-source .NET libraries, including recommended metadata for all packages published publicly on NuGet.org.</span></span>

### <a name="dependencies"></a>[<span data-ttu-id="4e43d-112">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="4e43d-112">Dependencies</span></span>](./dependencies.md)

<span data-ttu-id="4e43d-113">Mit NuGet ist es ganz einfach, vorhandene Pakete beim Erstellen einer.NET-Bibliothek zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e43d-113">NuGet makes it easy to use existing packages when building a .NET library.</span></span> <span data-ttu-id="4e43d-114">Erfahren Sie mehr über die häufigen Problemquellen von NuGet-Abhängigkeiten und wie Sie diese vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="4e43d-114">Learn about NuGet dependencies' common sources of friction and how to avoid them.</span></span>

### <a name="source-link"></a>[<span data-ttu-id="4e43d-115">Quelllink</span><span class="sxs-lookup"><span data-stu-id="4e43d-115">Source Link</span></span>](./sourcelink.md)

<span data-ttu-id="4e43d-116">SourceLink ist ein großartiges Werkzeug, das es Benutzern Ihrer .NET-Bibliothek ermöglicht, während des Debuggens in den Quellcode zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="4e43d-116">Source Link is a great tool that allows users of your .NET library to step into its source code while debugging.</span></span> <span data-ttu-id="4e43d-117">Dieser Artikel bietet eine Übersicht darüber, was SourceLink ist, und warum Sie es verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="4e43d-117">This article is an overview of what Source Link is and why you should use it.</span></span>

### <a name="publishing"></a>[<span data-ttu-id="4e43d-118">Veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="4e43d-118">Publishing</span></span>](./publish-nuget-package.md)

<span data-ttu-id="4e43d-119">NuGet.org ist zwar das bekannteste und am weitesten verbreitete Repository, es gibt jedoch viele Möglichkeiten, NuGet-Pakete zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4e43d-119">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages.</span></span> <span data-ttu-id="4e43d-120">Erfahren Sie mehr über die verschiedenen verfügbaren NuGet-Paketrepositorys und bewährte Sicherheitsmethoden für die Veröffentlichung einer .NET-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="4e43d-120">Learn about the different NuGet package repositories available, and security best practices for publishing a .NET library.</span></span>

## <a name="versioning"></a>[<span data-ttu-id="4e43d-121">Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="4e43d-121">Versioning</span></span>](./versioning.md)

<span data-ttu-id="4e43d-122">Gute .NET-Bibliotheken entwickeln sich im Laufe der Zeit weiter, indem in späteren Versionen Funktionen hinzugefügt, Fehler behoben und die Leistung verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="4e43d-122">Good .NET libraries evolve over time, adding features, fixing bugs, and improving performance in later releases.</span></span> <span data-ttu-id="4e43d-123">Erfahren Sie mehr über die verschiedenen Versionsnummern und wie Sie Entwickler über aktuelle Änderungen informieren können.</span><span class="sxs-lookup"><span data-stu-id="4e43d-123">Learn about the various version numbers and how to communicate breaking changes to developers.</span></span>

### <a name="breaking-changes"></a>[<span data-ttu-id="4e43d-124">Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="4e43d-124">Breaking changes</span></span>](./breaking-changes.md)

<span data-ttu-id="4e43d-125">Es ist wichtig für eine .NET-Bibliothek, ein Gleichgewicht zwischen Stabilität für bestehende Benutzer und Innovation für die Zukunft zu finden.</span><span class="sxs-lookup"><span data-stu-id="4e43d-125">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="4e43d-126">Erfahren Sie mehr über die verschiedenen Arten von Änderungen und Strategien zum Hinzufügen neuer Funktionen unter Beibehaltung der Abwärtskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="4e43d-126">Learn about the different kinds of breaking changes and strategies for adding new features while maintaining backwards compatibility.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4e43d-127">[Zurück](index.md)
>[Weiter](cross-platform-targeting.md)</span><span class="sxs-lookup"><span data-stu-id="4e43d-127">[Previous](index.md)
[Next](cross-platform-targeting.md)</span></span>
