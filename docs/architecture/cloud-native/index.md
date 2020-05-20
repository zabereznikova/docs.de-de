---
title: Entwickeln cloudnativer .NET-Anwendungen für Azure
description: Leitfaden zum Erstellen cloudnativer Anwendungen, die Container, Microservices und serverlose Features von Azure nutzen.
author: ardalis
ms.date: 05/13/2020
ms.openlocfilehash: 1607c1bbcc9bbb3c9fe19840a2827aa5ea083728
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613997"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="a9222-103">Entwickeln cloudnativer .NET-Anwendungen für Azure</span><span class="sxs-lookup"><span data-stu-id="a9222-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![Titelbild](./media/cover.png)

<span data-ttu-id="a9222-105">**Edition 1.0**</span><span class="sxs-lookup"><span data-stu-id="a9222-105">**EDITION v.1.0**</span></span>

<span data-ttu-id="a9222-106">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="a9222-106">PUBLISHED BY</span></span>

<span data-ttu-id="a9222-107">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="a9222-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="a9222-108">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="a9222-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="a9222-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="a9222-109">One Microsoft Way</span></span>

<span data-ttu-id="a9222-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="a9222-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="a9222-111">Copyright &copy; 2020 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="a9222-111">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="a9222-112">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="a9222-112">All rights reserved.</span></span> <span data-ttu-id="a9222-113">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="a9222-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="a9222-114">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="a9222-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="a9222-115">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a9222-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="a9222-116">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="a9222-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="a9222-117">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="a9222-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="a9222-118">Microsoft und die auf der Webseite „Marken“ unter https://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="a9222-118">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="a9222-119">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="a9222-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="a9222-120">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="a9222-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="a9222-121">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a9222-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="a9222-122">Autoren:</span><span class="sxs-lookup"><span data-stu-id="a9222-122">Authors:</span></span>

> <span data-ttu-id="a9222-123">**Rob Vettor**, Principal Cloud System Architect und IP Architect bei Microsoft – [thinkingincloudnative.com](http://thinkingincloudnative.com/about/)</span><span class="sxs-lookup"><span data-stu-id="a9222-123">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="a9222-124">**Steve „ardalis“ Smith**, Software Architect und Trainer – [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="a9222-124">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="a9222-125">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="a9222-125">Participants and Reviewers:</span></span>

> <span data-ttu-id="a9222-126">**Cesar De la Torre**, Principal Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9222-126">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="a9222-127">**Nish Anil**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9222-127">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="a9222-128">**Jeremy Likness**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9222-128">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="a9222-129">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9222-129">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="a9222-130">Editoren:</span><span class="sxs-lookup"><span data-stu-id="a9222-130">Editors:</span></span>

> <span data-ttu-id="a9222-131">**Maira Wenzel**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9222-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="a9222-132">Version</span><span class="sxs-lookup"><span data-stu-id="a9222-132">Version</span></span>

<span data-ttu-id="a9222-133">Dieser Leitfaden wurde für **.NET Core 3.1** geschrieben und enthält viele weitere Updates zu ähnlichen Technologien (wie Azure und entsprechende Drittanbietertechnologien), die zeitgleich mit .NET Core 3.1 veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="a9222-133">This guide has been written to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="a9222-134">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="a9222-134">Who should use this guide</span></span>

<span data-ttu-id="a9222-135">Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die lernen möchten, wie Anwendungen für die Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a9222-135">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="a9222-136">Technische Entscheidungsträger, die überlegen, ihre Anwendungen mithilfe eines cloudnativen Ansatzes zu erstellen, sind eine sekundäre Zielgruppe.</span><span class="sxs-lookup"><span data-stu-id="a9222-136">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="a9222-137">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="a9222-137">How you can use this guide</span></span>

<span data-ttu-id="a9222-138">In diesem Leitfaden wird zunächst der Begriff „Cloudnativ“ definiert und eine Referenzanwendung vorgestellt, die mithilfe cloudnativer Prinzipien und Technologien erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a9222-138">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="a9222-139">Nach diesen ersten beiden Kapiteln ist das Buch in spezifische Kapitel unterteilt, die sich mit gängigen Themen im Bezug zu den meisten cloudnativen Anwendungen befassen.</span><span class="sxs-lookup"><span data-stu-id="a9222-139">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="a9222-140">Sie können zu einem dieser Kapitel springen, um die folgenden cloudnativen Ansätze kennenzulernen:</span><span class="sxs-lookup"><span data-stu-id="a9222-140">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="a9222-141">Daten und Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="a9222-141">Data and data access</span></span>
- <span data-ttu-id="a9222-142">Kommunikationsmuster</span><span class="sxs-lookup"><span data-stu-id="a9222-142">Communication patterns</span></span>
- <span data-ttu-id="a9222-143">Skalierung und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="a9222-143">Scaling and scalability</span></span>
- <span data-ttu-id="a9222-144">Anwendungsresilienz</span><span class="sxs-lookup"><span data-stu-id="a9222-144">Application resiliency</span></span>
- <span data-ttu-id="a9222-145">Überwachung und Integrität</span><span class="sxs-lookup"><span data-stu-id="a9222-145">Monitoring and health</span></span>
- <span data-ttu-id="a9222-146">Identität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a9222-146">Identity and security</span></span>
- <span data-ttu-id="a9222-147">DevOps</span><span class="sxs-lookup"><span data-stu-id="a9222-147">DevOps</span></span>

<span data-ttu-id="a9222-148">Dieser Leitfaden ist sowohl im PDF-Format als auch online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9222-148">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="a9222-149">Sie können dieses Dokument oder Links zur Onlineversion an Ihr Team weiterleiten, um ein allgemeines Verständnis dieser Themen sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a9222-149">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="a9222-150">Die meisten dieser Themen profitieren von einem einheitlichen Verständnis der zugrunde liegenden Prinzipien und Muster sowie der Nachteile einiger Entscheidungen, die in Relation zu diesen Entscheidungen stehen.</span><span class="sxs-lookup"><span data-stu-id="a9222-150">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="a9222-151">Das Ziel dieses Dokuments ist es, Teams und Teamleiter mit den Informationen auszustatten, die sie benötigen, um fundierte Entscheidungen bezüglich der Architektur, der Entwicklung und des Hostings ihrer Anwendungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="a9222-151">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="a9222-152">Senden Sie uns Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="a9222-152">Send your feedback</span></span>

<span data-ttu-id="a9222-153">Dieses Buch und die dazugehörigen Beispiele werden ständig weiterentwickelt, deshalb freuen wir uns über Ihr Feedback.</span><span class="sxs-lookup"><span data-stu-id="a9222-153">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="a9222-154">Wenn Sie Anmerkungen zur Verbesserung dieses Buchs haben, nutzen Sie den Feedbackabschnitt, der unten auf jeder Seite zu finden ist und über den [GitHub-Issues](https://github.com/dotnet/docs/issues) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a9222-154">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="a9222-155">Nächste</span><span class="sxs-lookup"><span data-stu-id="a9222-155">Next</span></span>](introduction.md)
