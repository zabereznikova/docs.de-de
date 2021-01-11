---
title: ASP.NET Core gRPC für WCF-Entwickler – gRPC für WCF-Entwickler
description: Einführung in die Erstellung von gRPC-Diensten in ASP.NET Core 5.0 für WCF-Entwickler
ms.date: 01/06/2021
ms.openlocfilehash: 26cce6bb784c08a5b59623ff5882fcf2fbb9e9ac
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970192"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="61f6b-103">ASP.NET Core gRPC für WCF-Entwickler</span><span class="sxs-lookup"><span data-stu-id="61f6b-103">ASP.NET Core gRPC for WCF Developers</span></span>

![Titelbild](./media/cover.png)

<span data-ttu-id="61f6b-105">EDITION v1.0.1: auf ASP.NET Core 5.0 aktualisiert</span><span class="sxs-lookup"><span data-stu-id="61f6b-105">EDITION v1.0.1 - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="61f6b-106">Informationen zu den Buchaktualisierungen und Communitybeiträgen finden Sie im [Änderungsprotokoll](https://aka.ms/grpc-ebook-changelog).</span><span class="sxs-lookup"><span data-stu-id="61f6b-106">Refer [changelog](https://aka.ms/grpc-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="61f6b-107">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="61f6b-107">PUBLISHED BY</span></span>

<span data-ttu-id="61f6b-108">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="61f6b-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="61f6b-109">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="61f6b-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="61f6b-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="61f6b-110">One Microsoft Way</span></span>

<span data-ttu-id="61f6b-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="61f6b-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="61f6b-112">Copyright © 2021 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="61f6b-112">Copyright © 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="61f6b-113">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="61f6b-113">All rights reserved.</span></span> <span data-ttu-id="61f6b-114">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="61f6b-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="61f6b-115">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="61f6b-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="61f6b-116">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="61f6b-116">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="61f6b-117">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="61f6b-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="61f6b-118">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="61f6b-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="61f6b-119">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="61f6b-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="61f6b-120">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="61f6b-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="61f6b-121">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="61f6b-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="61f6b-122">Autoren:</span><span class="sxs-lookup"><span data-stu-id="61f6b-122">Authors:</span></span>

> <span data-ttu-id="61f6b-123">**Mark Rendle** – Chief Technical Officer – [Visual ReCode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="61f6b-123">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="61f6b-124">**Miranda Steiner** – Technical Author</span><span class="sxs-lookup"><span data-stu-id="61f6b-124">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="61f6b-125">Editor:</span><span class="sxs-lookup"><span data-stu-id="61f6b-125">Editor:</span></span>

> <span data-ttu-id="61f6b-126">**Maira Wenzel** – Senior Content Developer – Microsoft</span><span class="sxs-lookup"><span data-stu-id="61f6b-126">**Maira Wenzel** - Sr. Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="61f6b-127">Einführung</span><span class="sxs-lookup"><span data-stu-id="61f6b-127">Introduction</span></span>

<span data-ttu-id="61f6b-128">gRPC ist ein modernes Framework zur Erstellung vernetzter Dienste und verteilter Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="61f6b-128">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="61f6b-129">Stellen Sie sich die Leistung der NetTCP-Bindungen der Windows Communication Foundation (WCF) in Kombination mit der plattformübergreifenden Interoperabilität von SOAP vor.</span><span class="sxs-lookup"><span data-stu-id="61f6b-129">Imagine the performance of Windows Communication Foundation (WCF) NetTCP bindings, combined with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="61f6b-130">gRPC baut auf HTTP/2 und dem Protobuf-Nachrichtencodierungsprotokoll auf, um eine hochleistungsfähige, bandbreitenarme Kommunikation zwischen Anwendungen und Diensten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="61f6b-130">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="61f6b-131">Der Dienst unterstützt die Generierung von Server- und Clientcode in den gängigsten Programmiersprachen und Plattformen, einschließlich .NET, Java, Python, Node.js, Go und C++.</span><span class="sxs-lookup"><span data-stu-id="61f6b-131">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, and C++.</span></span> <span data-ttu-id="61f6b-132">Mit der erstklassigen Unterstützung für gRPC in ASP.NET Core 5.0, neben den bestehenden gRPC-Tools und -Bibliotheken für .NET Framework 4.x, gilt es als eine ausgezeichnete Alternative zur WCF für Entwicklungsteams, die .NET in ihren Organisationen einsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="61f6b-132">With the first-class support for gRPC in ASP.NET Core 5.0, alongside the existing gRPC tools and libraries for .NET Framework 4.x, it's an excellent alternative to WCF for development teams looking to adopt .NET in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="61f6b-133">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="61f6b-133">Who should use this guide</span></span>

<span data-ttu-id="61f6b-134">Dieser Leitfaden richtet sich an Entwickler, die in .NET Framework oder .NET arbeiten, zuvor WCF verwendet haben und ihre Anwendungen auf eine moderne RPC-Umgebung für .NET Core 3.0 und spätere Versionen migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61f6b-134">This guide was written for developers working in .NET Framework or .NET who have previously used WCF, and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="61f6b-135">Der Leitfaden ist ebenfalls nützlich, wenn Sie ein Upgrade auf .NET 5 durchführen oder in Betracht ziehen und die integrierten gRPC-Tools verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="61f6b-135">More generally, if you are upgrading, or considering upgrading, to .NET 5, and you want to use the built-in gRPC tools, this guide is also useful.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="61f6b-136">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="61f6b-136">How you can use this guide</span></span>

<span data-ttu-id="61f6b-137">Dies ist eine kurze Einführung in das Erstellen von gRPC-Diensten in ASP.NET Core 5.0 mit einem besonderen Verweis auf die WCF als analoge Plattform.</span><span class="sxs-lookup"><span data-stu-id="61f6b-137">This is a short introduction to building gRPC Services in ASP.NET Core 5.0, with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="61f6b-138">Darin werden die Prinzipien von gRPC erläutert, indem die einzelnen Konzepte den entsprechenden Features von WCF zugeordnet werden, und es wird ein Leitfaden zum Migrieren einer vorhandenen WCF-Anwendung zu gRPC geboten.</span><span class="sxs-lookup"><span data-stu-id="61f6b-138">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="61f6b-139">Sie ist auch für Entwickler nützlich, die WCF-Kenntnisse besitzen und gRPC erlernen möchten, um neue Dienste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61f6b-139">It's also useful for developers who have experience with WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="61f6b-140">Die Beispielanwendungen können Sie als Vorlage oder Verweis für Ihre eigenen Projekte verwenden, zudem können Sie Code aus dem Buch oder den Beispielen kopieren und diesen so wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="61f6b-140">You can use the sample applications as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="61f6b-141">Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="61f6b-141">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="61f6b-142">Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung der Architekturmuster und -praktiken gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="61f6b-142">Having everybody working from a common set of terms and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="61f6b-143">Verweise</span><span class="sxs-lookup"><span data-stu-id="61f6b-143">References</span></span>

- <span data-ttu-id="61f6b-144">**Website zu gRPC**
  <https://grpc.io></span><span class="sxs-lookup"><span data-stu-id="61f6b-144">**gRPC website**
<https://grpc.io></span></span>
- <span data-ttu-id="61f6b-145">**.NET 5 für Server-Apps im Vergleich zum .NET Framework**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="61f6b-145">**Choosing between .NET 5 and .NET Framework for server apps**
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="61f6b-146">Nächste</span><span class="sxs-lookup"><span data-stu-id="61f6b-146">Next</span></span>](introduction.md)
