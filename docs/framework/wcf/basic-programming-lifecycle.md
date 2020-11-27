---
title: Grundlegender Programmierlebenszyklus
description: Erfahren Sie mehr über die Aufgaben zum Erstellen einer WCF-Anwendung. WCF ermöglicht Apps die Kommunikation auf demselben Computer, über Netzwerke oder auf verschiedenen Anwendungsplattformen.
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: f958bd06f617a5648b31332ebe9e7662d45cd241
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294845"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="768e2-104">Grundlegender Programmierlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="768e2-104">Basic Programming Lifecycle</span></span>

<span data-ttu-id="768e2-105">Mit Windows Communication Foundation (WCF) können Anwendungen kommunizieren, ob Sie sich auf demselben Computer, über das Internet oder auf verschiedenen Anwendungsplattformen befinden.</span><span class="sxs-lookup"><span data-stu-id="768e2-105">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="768e2-106">In diesem Thema werden die Aufgaben erläutert, die zum Erstellen einer WCF-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="768e2-106">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="768e2-107">Eine funktionierende Beispielanwendung finden Sie unter [Getting Started Tutorial](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="768e2-107">For a working sample application, see [Getting Started Tutorial](getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="768e2-108">Grundlegende Aufgaben</span><span class="sxs-lookup"><span data-stu-id="768e2-108">The Basic Tasks</span></span>  

 <span data-ttu-id="768e2-109">Die folgenden grundlegenden Aufgaben müssen in der angegebenen Reihenfolge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="768e2-109">The basic tasks to perform are, in order:</span></span>  
  
1. <span data-ttu-id="768e2-110">Definieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="768e2-110">Define the service contract.</span></span> <span data-ttu-id="768e2-111">Ein Dienstvertrag gibt die Signatur eines Diensts, die Daten, die ausgetauscht werden, sowie andere vertraglich erforderliche Daten an.</span><span class="sxs-lookup"><span data-stu-id="768e2-111">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="768e2-112">Weitere Informationen finden Sie unter [Entwerfen von Dienstverträgen](designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="768e2-112">For more information, see [Designing Service Contracts](designing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="768e2-113">Implementieren Sie den Vertrag.</span><span class="sxs-lookup"><span data-stu-id="768e2-113">Implement the contract.</span></span> <span data-ttu-id="768e2-114">Zum Implementieren eines Dienstvertrags erstellen Sie eine Klasse, die den Vertrag implementiert, und geben Sie das benutzerdefinierte Verhalten der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="768e2-114">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="768e2-115">Weitere Informationen finden Sie unter [Implementieren von Dienstverträgen](implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="768e2-115">For more information, see [Implementing Service Contracts](implementing-service-contracts.md).</span></span>  
  
3. <span data-ttu-id="768e2-116">Konfigurieren Sie den Dienst, indem Sie Endpunkte und andere Verhaltensinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="768e2-116">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="768e2-117">Weitere Informationen finden Sie unter [Konfigurieren von Diensten](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="768e2-117">For more information, see [Configuring Services](configuring-services.md).</span></span>  
  
4. <span data-ttu-id="768e2-118">Hosten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="768e2-118">Host the service.</span></span> <span data-ttu-id="768e2-119">Weitere Informationen finden Sie unter [Hostingdienste](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="768e2-119">For more information, see [Hosting Services](hosting-services.md).</span></span>  
  
5. <span data-ttu-id="768e2-120">Erstellen Sie eine Clientanwendung.</span><span class="sxs-lookup"><span data-stu-id="768e2-120">Build a client application.</span></span> <span data-ttu-id="768e2-121">Weitere Informationen finden Sie unter [Building Clients](building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="768e2-121">For more information, see [Building Clients](building-clients.md).</span></span>  
  
 <span data-ttu-id="768e2-122">Obwohl die Themen in diesem Abschnitt dieser Reihenfolge entsprechen, beginnen einige Szenarien nicht am Anfang.</span><span class="sxs-lookup"><span data-stu-id="768e2-122">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="768e2-123">Wenn Sie beispielsweise einen Client für einen bereits vorhandenen Dienst erstellen möchten, beginnen Sie bei Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="768e2-123">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="768e2-124">Wenn Sie hingegen einen Dienst erstellen, den andere verwenden, können Sie Schritt 5 überspringen.</span><span class="sxs-lookup"><span data-stu-id="768e2-124">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="768e2-125">Wenn Sie mit der Entwicklung von Dienstverträgen vertraut sind, können Sie auch [die Einführung in die Erweiterbarkeit](introduction-to-extensibility.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="768e2-125">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](introduction-to-extensibility.md).</span></span> <span data-ttu-id="768e2-126">Wenn Sie Probleme mit Ihrem Dienst haben, überprüfen Sie den [Schnellstart zur Problem](wcf-troubleshooting-quickstart.md) Behandlung von WCF, um festzustellen, ob andere Probleme dieselben oder ähnliche Probleme haben.</span><span class="sxs-lookup"><span data-stu-id="768e2-126">If you have problems with your service, check [WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="768e2-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="768e2-127">See also</span></span>

- [<span data-ttu-id="768e2-128">Implementieren von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="768e2-128">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
