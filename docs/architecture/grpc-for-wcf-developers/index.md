---
title: ASP.NET Core gRPC für WCF-Entwickler – gRPC für WCF-Entwickler
description: Einführung in die Erstellung von gRPC-Diensten in ASP.NET Core 3.0 für WCF-Entwickler
ms.date: 09/02/2019
ms.openlocfilehash: c9cc5ef9c06d5262fb85850f8a3b178d46e5c6fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689276"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="e9390-103">ASP.NET Core gRPC für WCF-Entwickler</span><span class="sxs-lookup"><span data-stu-id="e9390-103">ASP.NET Core gRPC for WCF Developers</span></span>

![Titelbild](./media/cover.png)

<span data-ttu-id="e9390-105">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="e9390-105">PUBLISHED BY</span></span>

<span data-ttu-id="e9390-106">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="e9390-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="e9390-107">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="e9390-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="e9390-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e9390-108">One Microsoft Way</span></span>

<span data-ttu-id="e9390-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="e9390-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="e9390-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="e9390-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="e9390-111">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="e9390-111">All rights reserved.</span></span> <span data-ttu-id="e9390-112">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e9390-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="e9390-113">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="e9390-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="e9390-114">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e9390-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="e9390-115">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="e9390-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="e9390-116">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="e9390-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="e9390-117">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="e9390-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="e9390-118">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="e9390-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="e9390-119">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="e9390-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="e9390-120">Autoren:</span><span class="sxs-lookup"><span data-stu-id="e9390-120">Authors:</span></span>

> <span data-ttu-id="e9390-121">**Mark Rendle** – Chief Technical Officer – [Visual ReCode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="e9390-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="e9390-122">**Miranda Steiner** – Technical Author</span><span class="sxs-lookup"><span data-stu-id="e9390-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="e9390-123">Editor:</span><span class="sxs-lookup"><span data-stu-id="e9390-123">Editor:</span></span>

> <span data-ttu-id="e9390-124">**Maira Wenzel** – Senior Content Developer – Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9390-124">**Maira Wenzel** - Sr. Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="e9390-125">Einführung</span><span class="sxs-lookup"><span data-stu-id="e9390-125">Introduction</span></span>

<span data-ttu-id="e9390-126">gRPC ist ein modernes Framework zur Erstellung vernetzter Dienste und verteilter Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e9390-126">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="e9390-127">Stellen Sie sich die Leistung der NetTCP-Bindungen der Windows Communication Foundation (WCF) in Kombination mit der plattformübergreifenden Interoperabilität von SOAP vor.</span><span class="sxs-lookup"><span data-stu-id="e9390-127">Imagine the performance of Windows Communication Foundation (WCF) NetTCP bindings, combined with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="e9390-128">gRPC baut auf HTTP/2 und dem Protobuf-Nachrichtencodierungsprotokoll auf, um eine hochleistungsfähige, bandbreitenarme Kommunikation zwischen Anwendungen und Diensten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e9390-128">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="e9390-129">Der Dienst unterstützt die Generierung von Server- und Clientcode in den gängigsten Programmiersprachen und Plattformen, einschließlich .NET, Java, Python, Node.js, Go und C++.</span><span class="sxs-lookup"><span data-stu-id="e9390-129">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, and C++.</span></span> <span data-ttu-id="e9390-130">Mit der erstklassigen Unterstützung für gRPC in ASP.NET Core 3.0, neben den bestehenden gRPC-Tools und -Bibliotheken für .NET Framework 4.x, gilt es als eine ausgezeichnete Alternative zur WCF für Entwicklungsteams, die .NET Core in ihren Organisationen einsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="e9390-130">With the first-class support for gRPC in ASP.NET Core 3.0, alongside the existing gRPC tools and libraries for .NET Framework 4.x, it's an excellent alternative to WCF for development teams looking to adopt .NET Core in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="e9390-131">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="e9390-131">Who should use this guide</span></span>

<span data-ttu-id="e9390-132">Dieser Leitfaden richtet sich an Entwickler, die in .NET Framework oder .NET Core arbeiten, zuvor WCF verwendet haben und ihre Anwendungen auf eine moderne RPC-Umgebung für .NET Core 3.0 und spätere Versionen migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e9390-132">This guide was written for developers working in .NET Framework or .NET Core who have previously used WCF, and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="e9390-133">Der Leitfaden ist ebenfalls nützlich, wenn Sie ein Upgrade auf .NET Core 3.0 durchführen oder in Betracht ziehen und die integrierten gRPC-Tools verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e9390-133">More generally, if you are upgrading, or considering upgrading, to .NET Core 3.0, and you want to use the built-in gRPC tools, this guide is also useful.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="e9390-134">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="e9390-134">How you can use this guide</span></span>

<span data-ttu-id="e9390-135">Dies ist eine kurze Einführung in das Erstellen von gRPC-Diensten in ASP.NET Core 3.0 mit einem besonderen Verweis auf die WCF als analoge Plattform.</span><span class="sxs-lookup"><span data-stu-id="e9390-135">This is a short introduction to building gRPC Services in ASP.NET Core 3.0, with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="e9390-136">Darin werden die Prinzipien von gRPC erläutert, indem die einzelnen Konzepte den entsprechenden Features von WCF zugeordnet werden, und es wird ein Leitfaden zum Migrieren einer vorhandenen WCF-Anwendung zu gRPC geboten.</span><span class="sxs-lookup"><span data-stu-id="e9390-136">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="e9390-137">Sie ist auch für Entwickler nützlich, die WCF-Kenntnisse besitzen und gRPC erlernen möchten, um neue Dienste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9390-137">It's also useful for developers who have experience with WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="e9390-138">Die Beispielanwendungen können Sie als Vorlage oder Verweis für Ihre eigenen Projekte verwenden, zudem können Sie Code aus dem Buch oder den Beispielen kopieren und diesen so wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="e9390-138">You can use the sample applications as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="e9390-139">Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="e9390-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="e9390-140">Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung der Architekturmuster und -praktiken gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="e9390-140">Having everybody working from a common set of terms and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="e9390-141">Verweise</span><span class="sxs-lookup"><span data-stu-id="e9390-141">References</span></span>

- <span data-ttu-id="e9390-142">**Website zu gRPC**
  <https://grpc.io></span><span class="sxs-lookup"><span data-stu-id="e9390-142">**gRPC website**
<https://grpc.io></span></span>
- <span data-ttu-id="e9390-143">**Entscheidung zwischen .NET Core und .NET Framework für Server-Apps**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="e9390-143">**Choosing between .NET Core and .NET Framework for server apps**
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="e9390-144">Nächste</span><span class="sxs-lookup"><span data-stu-id="e9390-144">Next</span></span>](introduction.md)
