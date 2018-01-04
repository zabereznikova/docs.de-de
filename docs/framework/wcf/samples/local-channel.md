---
title: Lokaler Kanal
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1298b4b96006837f0634040c5c615adfa3a1a11b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="local-channel"></a><span data-ttu-id="5d218-102">Lokaler Kanal</span><span class="sxs-lookup"><span data-stu-id="5d218-102">Local Channel</span></span>
<span data-ttu-id="5d218-103">Der lokale Kanal ist ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Transportkanal, der für die Kommunikation innerhalb derselben Anwendungsdomäne verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d218-103">Local Channel is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="5d218-104">Dies ist nützlich bei Szenarien, in denen der Client und der Dienst in der gleichen Anwendungsdomäne ausgeführt werden und der Mehraufwand eines normalen WCF-Kanalstapels (Serialisierung und Deserialisierung von Meldungen) vermieden werden muss.</span><span class="sxs-lookup"><span data-stu-id="5d218-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5d218-105">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="5d218-105">Demonstrates</span></span>  
 <span data-ttu-id="5d218-106">Lokaler Kanal</span><span class="sxs-lookup"><span data-stu-id="5d218-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="5d218-107">Diskussion</span><span class="sxs-lookup"><span data-stu-id="5d218-107">Discussion</span></span>  
 <span data-ttu-id="5d218-108">Das Beispiel umfasst zwei Projektdateien.</span><span class="sxs-lookup"><span data-stu-id="5d218-108">The sample consists of two project files:</span></span>  
  
-   <span data-ttu-id="5d218-109">**LocalChannel**: die programmgesteuerte Darstellung des lokalen Kanals in der aktuellen Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="5d218-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="5d218-110">In diesem Projekt fügt die sendende Komponente die Nachricht einer Warteschlange im Arbeitsspeicher hinzu. Die empfangende Komponente ruft die Nachricht aus der Warteschlange ab, um sie zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="5d218-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
-   <span data-ttu-id="5d218-111">**ClientAndService**: dieses Projekt hostet einen Dienst in einer Konsolenanwendung und führt dann einen Client, um den Dienst von innerhalb der gleichen Anwendungsdomäne aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5d218-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="5d218-112">Aufgrund des Entwurfs des lokalen Kanals werden Kanalstapel und Serialisierungsvorgang ausgelassen, um die Geschwindigkeit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="5d218-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="5d218-113">Der lokale Transportkanal wird mit einer Warteschlange implementiert, mit der Dienstaufrufe vom Client zum Dienst transportiert und der Wert zum Client zurückgesendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d218-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="5d218-114">Im Beispiel werden die Objekte kopiert, statt Parameter und Rückgabewerte zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="5d218-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5d218-115">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="5d218-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5d218-116">Erstellen Sie die Projektmappe LocalChannel, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="5d218-116">Build and run the LocalChannel solution.</span></span>  
  
2.  <span data-ttu-id="5d218-117">Der Diensthost wird gestartet, und der Client ruft den Dienst mithilfe des lokalen Kanals auf.</span><span class="sxs-lookup"><span data-stu-id="5d218-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="5d218-118">Ein Konsolenfenster mit den Ergebnissen des Dienstaufrufs wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d218-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5d218-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5d218-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5d218-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5d218-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5d218-121">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5d218-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5d218-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5d218-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
