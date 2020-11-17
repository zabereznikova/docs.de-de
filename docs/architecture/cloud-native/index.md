---
title: Entwickeln cloudnativer .NET-Anwendungen für Azure
description: Leitfaden zum Erstellen cloudnativer Anwendungen, die Container, Microservices und serverlose Features von Azure nutzen.
author: ardalis
ms.date: 11/10/2020
ms.openlocfilehash: 673bfef27c3767f68b1c30d4383cee010ba377f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506648"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="f809b-103">Entwickeln cloudnativer .NET-Anwendungen für Azure</span><span class="sxs-lookup"><span data-stu-id="f809b-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![Titelbild](./media/cover.png)

<span data-ttu-id="f809b-105">**Edition v1.0**</span><span class="sxs-lookup"><span data-stu-id="f809b-105">**EDITION v1.0**</span></span>

<span data-ttu-id="f809b-106">Informationen zu den Buchaktualisierungen und Communitybeiträgen finden Sie im [Änderungsprotokoll](https://aka.ms/cn-ebook-changelog).</span><span class="sxs-lookup"><span data-stu-id="f809b-106">Refer [changelog](https://aka.ms/cn-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="f809b-107">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="f809b-107">PUBLISHED BY</span></span>

<span data-ttu-id="f809b-108">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="f809b-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="f809b-109">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="f809b-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="f809b-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="f809b-110">One Microsoft Way</span></span>

<span data-ttu-id="f809b-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="f809b-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="f809b-112">Copyright &copy; 2020 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="f809b-112">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="f809b-113">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="f809b-113">All rights reserved.</span></span> <span data-ttu-id="f809b-114">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="f809b-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="f809b-115">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="f809b-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="f809b-116">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f809b-116">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="f809b-117">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="f809b-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="f809b-118">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="f809b-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="f809b-119">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="f809b-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="f809b-120">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="f809b-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="f809b-121">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="f809b-121">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="f809b-122">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="f809b-122">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="f809b-123">Autoren:</span><span class="sxs-lookup"><span data-stu-id="f809b-123">Authors:</span></span>

> <span data-ttu-id="f809b-124">**Rob Vettor**, Principal Cloud System Architect und IP Architect bei Microsoft – [thinkingincloudnative.com](https://thinkingincloudnative.com/about/)</span><span class="sxs-lookup"><span data-stu-id="f809b-124">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="f809b-125">**Steve „ardalis“ Smith**, Software Architect und Trainer – [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="f809b-125">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="f809b-126">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="f809b-126">Participants and Reviewers:</span></span>

> <span data-ttu-id="f809b-127">**Cesar De la Torre**, Principal Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="f809b-127">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="f809b-128">**Nish Anil**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="f809b-128">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="f809b-129">**Jeremy Likness**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="f809b-129">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="f809b-130">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span><span class="sxs-lookup"><span data-stu-id="f809b-130">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="f809b-131">Editoren:</span><span class="sxs-lookup"><span data-stu-id="f809b-131">Editors:</span></span>

> <span data-ttu-id="f809b-132">**Maira Wenzel**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="f809b-132">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="f809b-133">Version</span><span class="sxs-lookup"><span data-stu-id="f809b-133">Version</span></span>

<span data-ttu-id="f809b-134">Dieser Leitfaden wurde für **.NET Core 3.1** geschrieben und enthält viele weitere Updates zu ähnlichen Technologien (wie Azure und entsprechende Drittanbietertechnologien), die zeitgleich mit .NET Core 3.1 veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="f809b-134">This guide has been written to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="f809b-135">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="f809b-135">Who should use this guide</span></span>

<span data-ttu-id="f809b-136">Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die lernen möchten, wie Anwendungen für die Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f809b-136">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="f809b-137">Technische Entscheidungsträger, die überlegen, ihre Anwendungen mithilfe eines cloudnativen Ansatzes zu erstellen, sind eine sekundäre Zielgruppe.</span><span class="sxs-lookup"><span data-stu-id="f809b-137">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="f809b-138">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="f809b-138">How you can use this guide</span></span>

<span data-ttu-id="f809b-139">In diesem Leitfaden wird zunächst der Begriff „Cloudnativ“ definiert und eine Referenzanwendung vorgestellt, die mithilfe cloudnativer Prinzipien und Technologien erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f809b-139">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="f809b-140">Nach diesen ersten beiden Kapiteln ist das Buch in spezifische Kapitel unterteilt, die sich mit gängigen Themen im Bezug zu den meisten cloudnativen Anwendungen befassen.</span><span class="sxs-lookup"><span data-stu-id="f809b-140">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="f809b-141">Sie können zu einem dieser Kapitel springen, um die folgenden cloudnativen Ansätze kennenzulernen:</span><span class="sxs-lookup"><span data-stu-id="f809b-141">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="f809b-142">Daten und Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="f809b-142">Data and data access</span></span>
- <span data-ttu-id="f809b-143">Kommunikationsmuster</span><span class="sxs-lookup"><span data-stu-id="f809b-143">Communication patterns</span></span>
- <span data-ttu-id="f809b-144">Skalierung und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="f809b-144">Scaling and scalability</span></span>
- <span data-ttu-id="f809b-145">Anwendungsresilienz</span><span class="sxs-lookup"><span data-stu-id="f809b-145">Application resiliency</span></span>
- <span data-ttu-id="f809b-146">Überwachung und Integrität</span><span class="sxs-lookup"><span data-stu-id="f809b-146">Monitoring and health</span></span>
- <span data-ttu-id="f809b-147">Identität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f809b-147">Identity and security</span></span>
- <span data-ttu-id="f809b-148">DevOps</span><span class="sxs-lookup"><span data-stu-id="f809b-148">DevOps</span></span>

<span data-ttu-id="f809b-149">Dieser Leitfaden ist sowohl im [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf)-Format als auch online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f809b-149">This guide is available both in [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) form and online.</span></span> <span data-ttu-id="f809b-150">Sie können dieses Dokument oder Links zur Onlineversion an Ihr Team weiterleiten, um ein allgemeines Verständnis dieser Themen sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f809b-150">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="f809b-151">Die meisten dieser Themen profitieren von einem einheitlichen Verständnis der zugrunde liegenden Prinzipien und Muster sowie der Nachteile einiger Entscheidungen, die in Relation zu diesen Entscheidungen stehen.</span><span class="sxs-lookup"><span data-stu-id="f809b-151">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="f809b-152">Das Ziel dieses Dokuments ist es, Teams und Teamleiter mit den Informationen auszustatten, die sie benötigen, um fundierte Entscheidungen bezüglich der Architektur, der Entwicklung und des Hostings ihrer Anwendungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="f809b-152">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="f809b-153">Senden Sie uns Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="f809b-153">Send your feedback</span></span>

<span data-ttu-id="f809b-154">Dieses Buch und die dazugehörigen Beispiele werden ständig weiterentwickelt, deshalb freuen wir uns über Ihr Feedback.</span><span class="sxs-lookup"><span data-stu-id="f809b-154">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="f809b-155">Wenn Sie Anmerkungen zur Verbesserung dieses Buchs haben, nutzen Sie den Feedbackabschnitt, der unten auf jeder Seite zu finden ist und über den [GitHub-Issues](https://github.com/dotnet/docs/issues) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f809b-155">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="f809b-156">Nächste</span><span class="sxs-lookup"><span data-stu-id="f809b-156">Next</span></span>](introduction.md)
