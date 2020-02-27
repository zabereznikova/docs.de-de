---
title: Migrieren einer WCF-Lösung zu GrpC-GrpC für WCF-Entwickler
description: Vorgehensweise beim Migrieren verschiedener Typen von WCF-Diensten zu den entsprechenden Typen in GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: 12e724ab46a33547d352da7a604a5a994e617bc2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628513"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="33006-103">Migrieren einer WCF-Lösung zu gRPC</span><span class="sxs-lookup"><span data-stu-id="33006-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="33006-104">In diesem Kapitel wird beschrieben, wie Sie mit ASP.net Core 3,0-GrpC-Projekten arbeiten und die Migration verschiedener Typen von Windows Communication Foundation (WCF)-Diensten zu der GrpC-Entsprechung veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="33006-104">This chapter will describe how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of Windows Communication Foundation (WCF) services to the gRPC equivalent:</span></span>

- <span data-ttu-id="33006-105">Erstellen Sie ein ASP.net Core 3,0-GrpC-Projekt.</span><span class="sxs-lookup"><span data-stu-id="33006-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="33006-106">Einfache Anforderung/Antwort-Vorgänge an den unären GrpC-RPC.</span><span class="sxs-lookup"><span data-stu-id="33006-106">Simple request-reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="33006-107">Unidirektionale Vorgänge zum GrpC-clientstreaming von RPC.</span><span class="sxs-lookup"><span data-stu-id="33006-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="33006-108">Vollduplex Dienste für das bidirektionale Streaming von GrpC.</span><span class="sxs-lookup"><span data-stu-id="33006-108">Full-duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="33006-109">Es gibt auch einen Vergleich der Verwendung von Streamingdiensten im Vergleich zu wiederholten Feldern für die Rückgabe von Datasets, und es gibt eine Erörterung der Verwendung von Client Bibliotheken am Ende des Kapitels.</span><span class="sxs-lookup"><span data-stu-id="33006-109">There's also a comparison of using streaming services versus repeated fields for returning datasets, and there's a discussion of the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="33006-110">Bei der WCF-Beispielanwendung handelt es sich um einen minimalen Stub für eine Reihe von Aktienhandels Diensten.</span><span class="sxs-lookup"><span data-stu-id="33006-110">The sample WCF application is a minimal stub of a set of stock trading services.</span></span> <span data-ttu-id="33006-111">Er verwendet die Open Source-Container Bibliothek "Inversion of Control (IOC)" mit dem Namen "autofac" für die Abhängigkeitsinjektion.</span><span class="sxs-lookup"><span data-stu-id="33006-111">It uses the open-source Inversion of Control (IoC) container library called Autofac for dependency injection.</span></span> <span data-ttu-id="33006-112">Sie enthält drei Dienste, eine für jeden WCF-Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="33006-112">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="33006-113">Die Dienste werden in den folgenden Abschnitten ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="33006-113">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="33006-114">Sie können die Lösungen von [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) auf GitHub herunterladen.</span><span class="sxs-lookup"><span data-stu-id="33006-114">You can download the solutions from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="33006-115">Die Dienste verwenden gefälschte Daten, um externe Abhängigkeiten zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="33006-115">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="33006-116">Die Beispiele umfassen die WCF-und GrpC-Implementierungen der einzelnen Dienste.</span><span class="sxs-lookup"><span data-stu-id="33006-116">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="33006-117">[Zurück](ws-protocols.md)
>[Weiter](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="33006-117">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
