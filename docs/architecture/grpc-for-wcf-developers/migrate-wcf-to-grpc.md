---
title: Migrieren einer WCF-Lösung zu GrpC-GrpC für WCF-Entwickler
description: Vorgehensweise beim Migrieren verschiedener Typen von WCF-Diensten zu den entsprechenden Typen in GrpC.
ms.date: 12/15/2020
ms.openlocfilehash: 3bd35cb6119368ff3db3be9ab5fabf89f2652b29
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97937960"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="5bbfa-103">Migrieren einer WCF-Lösung zu gRPC</span><span class="sxs-lookup"><span data-stu-id="5bbfa-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="5bbfa-104">In diesem Kapitel wird beschrieben, wie Sie mit ASP.net Core 5,0-GrpC-Projekten arbeiten und die Migration verschiedener Typen von Windows Communication Foundation (WCF)-Diensten zu der GrpC-Entsprechung veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="5bbfa-104">This chapter will describe how to work with ASP.NET Core 5.0 gRPC projects and demonstrate migrating different types of Windows Communication Foundation (WCF) services to the gRPC equivalent:</span></span>

- <span data-ttu-id="5bbfa-105">Erstellen Sie ein ASP.net Core 5,0-GrpC-Projekt.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-105">Create an ASP.NET Core 5.0 gRPC project.</span></span>
- <span data-ttu-id="5bbfa-106">Einfache Anforderung/Antwort-Vorgänge an den unären GrpC-RPC.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-106">Simple request-reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="5bbfa-107">Unidirektionale Vorgänge zum GrpC-clientstreaming von RPC.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="5bbfa-108">Vollduplex Dienste für das bidirektionale Streaming von GrpC.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-108">Full-duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="5bbfa-109">Es gibt auch einen Vergleich der Verwendung von Streamingdiensten im Vergleich zu wiederholten Feldern für die Rückgabe von Datasets, und es gibt eine Erörterung der Verwendung von Client Bibliotheken am Ende des Kapitels.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-109">There's also a comparison of using streaming services versus repeated fields for returning datasets, and there's a discussion of the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="5bbfa-110">Bei der WCF-Beispielanwendung handelt es sich um einen minimalen Stub für eine Reihe von Aktienhandels Diensten.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-110">The sample WCF application is a minimal stub of a set of stock trading services.</span></span> <span data-ttu-id="5bbfa-111">Er verwendet die Open Source-Container Bibliothek "Inversion of Control (IOC)" mit dem Namen "autofac" für die Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-111">It uses the open-source Inversion of Control (IoC) container library called Autofac for dependency injection.</span></span> <span data-ttu-id="5bbfa-112">Sie enthält drei Dienste, eine für jeden WCF-Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-112">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="5bbfa-113">Die Dienste werden in den folgenden Abschnitten ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-113">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="5bbfa-114">Sie können die Lösungen von [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) auf GitHub herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-114">You can download the solutions from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="5bbfa-115">Die Dienste verwenden gefälschte Daten, um externe Abhängigkeiten zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-115">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="5bbfa-116">Die Beispiele umfassen die WCF-und GrpC-Implementierungen der einzelnen Dienste.</span><span class="sxs-lookup"><span data-stu-id="5bbfa-116">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5bbfa-117">[Zurück](ws-protocols.md)
>[Weiter](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="5bbfa-117">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
