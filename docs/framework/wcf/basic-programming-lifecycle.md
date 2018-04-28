---
title: Grundlegender Programmierlebenszyklus
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff735a8caf1fbaff636f94eee366b20c33d8f331
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="77055-102">Grundlegender Programmierlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="77055-102">Basic Programming Lifecycle</span></span>
<span data-ttu-id="77055-103">Mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] können Anwendungen miteinander zu kommunizieren, unabhängig davon, ob sie sich auf demselben Computer, im Internet oder auf verschiedenen Anwendungsplattformen befinden.</span><span class="sxs-lookup"><span data-stu-id="77055-103">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="77055-104">In diesem Thema werden die Aufgaben beschrieben, die zum Erstellen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="77055-104">This topic outlines the tasks that are required to build a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="77055-105">Eine funktionierende beispielanwendung finden Sie unter [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="77055-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="77055-106">Grundlegende Aufgaben</span><span class="sxs-lookup"><span data-stu-id="77055-106">The Basic Tasks</span></span>  
 <span data-ttu-id="77055-107">Die folgenden grundlegenden Aufgaben müssen in der angegebenen Reihenfolge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="77055-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="77055-108">Definieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="77055-108">Define the service contract.</span></span> <span data-ttu-id="77055-109">Ein Dienstvertrag gibt die Signatur eines Diensts, die Daten, die ausgetauscht werden, sowie andere vertraglich erforderliche Daten an.</span><span class="sxs-lookup"><span data-stu-id="77055-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="77055-110">Weitere Informationen finden Sie unter [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="77055-110">For more information, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="77055-111">Implementieren Sie den Vertrag.</span><span class="sxs-lookup"><span data-stu-id="77055-111">Implement the contract.</span></span> <span data-ttu-id="77055-112">Zum Implementieren eines Dienstvertrags erstellen Sie eine Klasse, die den Vertrag implementiert, und geben Sie das benutzerdefinierte Verhalten der Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="77055-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="77055-113">Weitere Informationen finden Sie unter [implementieren Dienstverträge](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="77055-113">For more information, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="77055-114">Konfigurieren Sie den Dienst, indem Sie Endpunkte und andere Verhaltensinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="77055-114">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="77055-115">Weitere Informationen finden Sie unter [Konfigurieren von Services](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="77055-115">For more information, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="77055-116">Hosten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="77055-116">Host the service.</span></span> <span data-ttu-id="77055-117">Weitere Informationen finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="77055-117">For more information, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="77055-118">Erstellen Sie eine Clientanwendung.</span><span class="sxs-lookup"><span data-stu-id="77055-118">Build a client application.</span></span> <span data-ttu-id="77055-119">Weitere Informationen finden Sie unter [Erstellen von Clients](../../../docs/framework/wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="77055-119">For more information, see [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="77055-120">Obwohl die Themen in diesem Abschnitt dieser Reihenfolge entsprechen, beginnen einige Szenarien nicht am Anfang.</span><span class="sxs-lookup"><span data-stu-id="77055-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="77055-121">Wenn Sie beispielsweise einen Client für einen bereits vorhandenen Dienst erstellen möchten, beginnen Sie bei Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="77055-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="77055-122">Wenn Sie hingegen einen Dienst erstellen, den andere verwenden, können Sie Schritt 5 überspringen.</span><span class="sxs-lookup"><span data-stu-id="77055-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="77055-123">Sobald Sie mit der Entwicklung von Dienstverträgen vertraut sind, können Sie auch eine Lesen [Einführung in die Erweiterbarkeit](../../../docs/framework/wcf/introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="77055-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="77055-124">Wenn Sie Probleme mit Ihrem Dienst haben, überprüfen Sie [Schnelleinstieg zur Problembehandlung in WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) um festzustellen, ob andere Benutzer die gleiche oder ähnliche Probleme haben.</span><span class="sxs-lookup"><span data-stu-id="77055-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77055-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77055-125">See Also</span></span>  
 [<span data-ttu-id="77055-126">Implementieren von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="77055-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
