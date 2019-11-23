---
title: Migrieren einer WCF-Lösung zu GrpC-GrpC für WCF-Entwickler
description: Vorgehensweise beim Migrieren verschiedener Typen von WCF-Diensten zu den entsprechenden Typen in GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: 33823d20e1593323a03da12981c5a4534c4d491a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971777"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="eb146-103">Migrieren einer WCF-Lösung zu gRPC</span><span class="sxs-lookup"><span data-stu-id="eb146-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="eb146-104">In diesem Kapitel wird erläutert, wie Sie mit ASP.net Core 3,0-GrpC-Projekten arbeiten und die Migration verschiedener WCF-Dienst Typen auf die entsprechende GrpC-Entsprechung veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="eb146-104">This chapter will look at how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of WCF service to the gRPC equivalent:</span></span>

- <span data-ttu-id="eb146-105">Erstellen Sie ein ASP.net Core 3,0-GrpC-Projekt.</span><span class="sxs-lookup"><span data-stu-id="eb146-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="eb146-106">Einfache Anforderung/Antwort-Vorgänge an den unären GrpC-RPC.</span><span class="sxs-lookup"><span data-stu-id="eb146-106">Simple Request-Reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="eb146-107">Unidirektionale Vorgänge zum GrpC-clientstreaming von RPC.</span><span class="sxs-lookup"><span data-stu-id="eb146-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="eb146-108">Vollständige Duplex Dienste für das bidirektionale Streaming von GrpC.</span><span class="sxs-lookup"><span data-stu-id="eb146-108">Full Duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="eb146-109">Es gibt auch einen Vergleich der Verwendung von Streamingdiensten im Vergleich zu wiederholten Feldern für die Rückgabe von Datasets und die Verwendung von Client Bibliotheken am Ende des Kapitels.</span><span class="sxs-lookup"><span data-stu-id="eb146-109">There's also a comparison of using streaming services versus repeated fields for returning data sets, and the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="eb146-110">Bei der WCF-Beispielanwendung handelt es sich um einen minimalen Stub für eine Reihe von Aktienhandels Diensten, die die Open Source-IoC-Container Bibliothek (Inversion of Control) mit dem Namen *autofac* für die Abhängigkeitsinjektion verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb146-110">The sample WCF application is a minimal stub of a set of stock trading services, using the open-source Inversion of Control (IoC) container library called *Autofac* for dependency injection.</span></span> <span data-ttu-id="eb146-111">Sie enthält drei Dienste, eine für jeden WCF-Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="eb146-111">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="eb146-112">Die Dienste werden in den folgenden Abschnitten ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="eb146-112">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="eb146-113">Die Lösungen können von [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) auf GitHub heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="eb146-113">The solutions can be downloaded from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="eb146-114">Die Dienste verwenden gefälschte Daten, um externe Abhängigkeiten zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="eb146-114">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="eb146-115">Die Beispiele umfassen die WCF-und GrpC-Implementierungen der einzelnen Dienste.</span><span class="sxs-lookup"><span data-stu-id="eb146-115">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="eb146-116">[Zurück](ws-protocols.md)
>[Weiter](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="eb146-116">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
