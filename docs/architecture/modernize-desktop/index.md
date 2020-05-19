---
title: Modernisieren von Desktop-Apps unter Windows 10 mit .NET Core 3.1
description: Hier erfahren Sie, wie Sie Desktop-Apps mit .NET Core 3.1 modernisieren können.
ms.date: 05/12/2020
ms.openlocfilehash: 5861f806a9158ef761c47bc23e51327d4e2d0480
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83422662"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a><span data-ttu-id="11f18-103">Modernisieren von Desktop-Apps unter Windows 10 mit .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="11f18-103">Modernizing Desktop Apps on Windows 10 with .NET Core 3.1</span></span>

![Screenshot: Cover des E-Books „Modernisieren von Desktop-Apps“](./media/modernizing-existing-desktop-apps-ebook-cover.png)

<span data-ttu-id="11f18-105">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="11f18-105">PUBLISHED BY</span></span>

<span data-ttu-id="11f18-106">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="11f18-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="11f18-107">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="11f18-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="11f18-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="11f18-108">One Microsoft Way</span></span>

<span data-ttu-id="11f18-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="11f18-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="11f18-110">Copyright © 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="11f18-110">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="11f18-111">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="11f18-111">All rights reserved.</span></span> <span data-ttu-id="11f18-112">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="11f18-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="11f18-113">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="11f18-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="11f18-114">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11f18-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="11f18-115">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="11f18-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="11f18-116">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="11f18-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="11f18-117">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="11f18-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="11f18-118">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="11f18-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="11f18-119">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="11f18-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="11f18-120">Mitautoren:</span><span class="sxs-lookup"><span data-stu-id="11f18-120">Co-Authors:</span></span>

> <span data-ttu-id="11f18-121">**Olia Gavrysh**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-121">**Olia Gavrysh**, Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="11f18-122">**Miguel Angel Castejón Dominguez**, Innovation Architect bei Kabel</span><span class="sxs-lookup"><span data-stu-id="11f18-122">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span></span>

<span data-ttu-id="11f18-123">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="11f18-123">Participants and reviewers:</span></span>

> <span data-ttu-id="11f18-124">**Maira Wenzel**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-124">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="11f18-125">**Andy De Gorge**, Senior Content Developer, .NET-Dokumentationsteam, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-125">**Andy De Gorge**, Senior Content Developer, .NET docs team, Microsoft</span></span>

> <span data-ttu-id="11f18-126">**Miguel Ramos**, Senior Program Manager, UWP-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-126">**Miguel Ramos**, Senior Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="11f18-127">**Adam Braden**, Principal Program Manager, UWP-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-127">**Adam Braden**, Principal Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="11f18-128">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-128">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT team, Microsoft</span></span>

> <span data-ttu-id="11f18-129">**Nish Anil**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-129">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="11f18-130">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-130">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span></span>

> <span data-ttu-id="11f18-131">**Scott Hunter**, Partner Director Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="11f18-131">**Scott Hunter**, Partner Director Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="11f18-132">**Marta Fuentes Lara**, Kabel</span><span class="sxs-lookup"><span data-stu-id="11f18-132">**Marta Fuentes Lara**, Kabel</span></span>

> <span data-ttu-id="11f18-133">**Raúl Fernández de Córdoba**, Kabel</span><span class="sxs-lookup"><span data-stu-id="11f18-133">**Raúl Fernández de Córdoba**, Kabel</span></span>

> <span data-ttu-id="11f18-134">**Antonio Manuel Fernández Cantos**, Kabel</span><span class="sxs-lookup"><span data-stu-id="11f18-134">**Antonio Manuel Fernández Cantos**, Kabel</span></span>

## <a name="introduction"></a><span data-ttu-id="11f18-135">Einführung</span><span class="sxs-lookup"><span data-stu-id="11f18-135">Introduction</span></span>

<span data-ttu-id="11f18-136">In diesem E-Book werden Strategien für die Migration vorhandener Desktop-Apps behandelt. Zu diesen zählen die Modernisierung und Integration der aktuellen Runtime, Sprache und Plattformfeatures.</span><span class="sxs-lookup"><span data-stu-id="11f18-136">This book is about strategies you can adopt to move your existing desktop applications through the path of modernization and incorporate the latest runtime, language, and platform features.</span></span> <span data-ttu-id="11f18-137">Sie werden feststellen, dass es keine Pauschallösung gibt, denn jede Anwendung ist einzigartig – genau wie Ihre Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="11f18-137">You'll discover that there's no unique recipe as each application is different, and so are your requirements and preferences.</span></span> <span data-ttu-id="11f18-138">Es gibt jedoch gängige Ansätze zum Hinzufügen neuer Features und Funktionen zu Ihren Anwendungen, die Ihnen nützlich sein können.</span><span class="sxs-lookup"><span data-stu-id="11f18-138">The good news is that there are common approaches you can apply to add new features and capabilities to your applications.</span></span> <span data-ttu-id="11f18-139">Bei einigen von diesen muss Ihr Code nur geringfügig geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11f18-139">Some of them won't even require major modifications of your code.</span></span> <span data-ttu-id="11f18-140">In diesem E-Book wird erklärt, wie alle diese Features unter der Haube funktionieren. Zudem werden Implementierungsverfahren erläutert.</span><span class="sxs-lookup"><span data-stu-id="11f18-140">In this book, we'll reveal how all those features work behind the scenes and explain the mechanics of their implementations.</span></span> <span data-ttu-id="11f18-141">Einige gängige Szenarios für die Modernisierung vorhandener Desktop-Apps werden ausführlich vorgestellt, sodass Sie sich Anregungen für Ihre eigenen Projekte holen können.</span><span class="sxs-lookup"><span data-stu-id="11f18-141">Moreover, you'll find some common scenarios for modernizing existing desktop applications shown in detail so you can find inspiration for evolving your projects.</span></span>

<span data-ttu-id="11f18-142">Der Microsoft-Ansatz für die Modernisierung vorhandener Apps ermöglicht es Ihnen, Ihren eigenen flexiblen Weg zu finden.</span><span class="sxs-lookup"><span data-stu-id="11f18-142">Microsoft's approach to modernizing existing applications is to give you the flexibility to create your own customized path.</span></span> <span data-ttu-id="11f18-143">Die in diesem Buch beschriebenen Modernisierungsstrategien sind größtenteils unabhängig.</span><span class="sxs-lookup"><span data-stu-id="11f18-143">All the modernization strategies described in this book are mostly independent.</span></span> <span data-ttu-id="11f18-144">Sie können diejenigen auswählen, die für Ihre Anwendung relevant sind, und die restlichen überspringen.</span><span class="sxs-lookup"><span data-stu-id="11f18-144">You can choose ones that are relevant for your application and skip others that aren't important for you.</span></span> <span data-ttu-id="11f18-145">Die Strategien können also so kombiniert werden, dass sie Ihren Anwendungsanforderungen bestmöglich gerecht werden.</span><span class="sxs-lookup"><span data-stu-id="11f18-145">In other words, you can mix and match the strategies to best address your application needs.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="11f18-146">Zielgruppe dieses Buchs</span><span class="sxs-lookup"><span data-stu-id="11f18-146">Who should use the book</span></span>

<span data-ttu-id="11f18-147">Dieses Buch richtet sich an Entwickler und Lösungsarchitekten, die vorhandene Windows Forms- und WPF-Desktop-Apps modernisieren möchten, um die Vorteile von .NET Core und Windows 10 zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="11f18-147">We wrote this book for developers and solution architects who want to modernize existing Windows Forms and WPF desktop applications to leverage the benefits of .NET Core and Windows 10.</span></span>

<span data-ttu-id="11f18-148">Auch Entscheidungsträgern in technischen Abteilungen kann dieses E-Book nützlich sein – zum Beispiel Unternehmensarchitekten, Entwicklungsleitern oder Führungskräften, die sich einen Überblick über die Vorteile verschaffen möchten, die die Aktualisierung vorhandener Desktop-Apps bietet.</span><span class="sxs-lookup"><span data-stu-id="11f18-148">You might also find this book useful if you're a technical decision maker, such as an enterprise architect or a development lead or director who wants an overview of the benefits of updating existing desktop applications.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="11f18-149">So verwenden Sie dieses Buch</span><span class="sxs-lookup"><span data-stu-id="11f18-149">How to use the book</span></span>

<span data-ttu-id="11f18-150">Dieses E-Book befasst sich mit dem „Warum“, das hinter der Modernisierung vorhandener Anwendungen steht, sowie mit den speziellen Vorteilen, die Ihnen .NET Core 3.1 und MSIX bieten, wenn Sie Ihre Desktop-Apps modernisieren.</span><span class="sxs-lookup"><span data-stu-id="11f18-150">This book addresses the "why"—why you might want to modernize your existing applications, and the specific benefits you get from using NET Core 3.1 and MSIX to modernize your desktop apps.</span></span> <span data-ttu-id="11f18-151">Der Inhalt des E-Books richtet sich an Architekten und technische Entscheidungsträger, die einen Überblick benötigen, sich aber nicht auf die Umsetzung und technische Details konzentrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="11f18-151">The content of the book is designed for architects and technical decision makers who want an overview, but who don't need to focus on implementation and technical, step-by-step details.</span></span>

<span data-ttu-id="11f18-152">In den verschiedenen Kapiteln finden Sie Codeausschnitte und Screenshots für Implementierungsbeispiele. In Kapitel 5 wird sogar ein vollständiger Migrationsprozess für Beispielanwendungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="11f18-152">Along the different chapters, sample implementation code snippets and screenshots are provided, with chapter 5 devoted to showcase a complete migration process for sample applications.</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="11f18-153">Was in diesem Buch nicht behandelt wird</span><span class="sxs-lookup"><span data-stu-id="11f18-153">What this book doesn't cover</span></span>

<span data-ttu-id="11f18-154">In diesem E-Book werden vor allem Lift-&-Shift-Szenarios behandelt, bei denen die Vorteile der Modernisierungsverfahren im Vordergrund stehen, für die Ihr Code nicht umgeschrieben werden muss.</span><span class="sxs-lookup"><span data-stu-id="11f18-154">This book covers a specific subset of scenarios that are focused on lift-and-shift scenarios, outlining the way to gain the benefits of modernizing without the effort of rewriting code.</span></span>

<span data-ttu-id="11f18-155">Die Entwicklung moderner Anwendungen mit .NET Core und der Einstieg in Windows Forms und WPF werden in diesem E-Book nicht thematisiert.</span><span class="sxs-lookup"><span data-stu-id="11f18-155">This book isn't about developing modern applications with .NET Core from scratch or about getting started with Windows Forms and WPF.</span></span> <span data-ttu-id="11f18-156">Der Fokus liegt darauf, wie Sie vorhandene Desktop-Apps mithilfe der neuesten Technologien für die Desktopentwicklung aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="11f18-156">It focuses on how you can update existing desktop applications with the latest technologies for desktop development.</span></span>

## <a name="samples-used-in-this-book"></a><span data-ttu-id="11f18-157">Beispiele in diesem E-Book</span><span class="sxs-lookup"><span data-stu-id="11f18-157">Samples used in this book</span></span>

<span data-ttu-id="11f18-158">Die Beispielanwendung `eShopModernizing` wird verwendet, um die für eine Modernisierung erforderlichen Schritte zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="11f18-158">To highlight the necessary steps to perform a modernization, we'll be using a sample application called `eShopModernizing`.</span></span> <span data-ttu-id="11f18-159">Diese Anwendung ist in zwei Varianten verfügbar: Windows Forms und WPF. Für beide wird ausführlich erläutert, wie der die Modernisierung auf .NET Core abläuft.</span><span class="sxs-lookup"><span data-stu-id="11f18-159">This application has two flavors, Windows Forms and WPF, and we'll show a step-by-step process on how to perform the modernization on both of them to .NET Core.</span></span>

<span data-ttu-id="11f18-160">Darüber hinaus finden Sie im GitHub-Repository für dieses E-Book die Ergebnisse des Prozesses, die für Sie relevant werden können, wenn Sie das ausführliche Tutorial befolgen.</span><span class="sxs-lookup"><span data-stu-id="11f18-160">Also, on the GitHub repository for this book, you'll find the results of the process, which you can consult with if you decide to follow the step-by-step tutorial.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="11f18-161">Senden Sie uns Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="11f18-161">Send your feedback</span></span>

<span data-ttu-id="11f18-162">Dieses Buch und die dazugehörigen Beispiele werden ständig weiterentwickelt, deshalb freuen wir uns über Ihr Feedback.</span><span class="sxs-lookup"><span data-stu-id="11f18-162">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="11f18-163">Wenn Sie Anmerkungen zur Verbesserung dieses Buchs haben, nutzen Sie den Feedbackabschnitt, der unten auf jeder Seite zu finden ist und über den [GitHub-Issues](https://github.com/dotnet/docs/issues) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="11f18-163">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="11f18-164">Nächste</span><span class="sxs-lookup"><span data-stu-id="11f18-164">Next</span></span>](why-modern-applications.md)
