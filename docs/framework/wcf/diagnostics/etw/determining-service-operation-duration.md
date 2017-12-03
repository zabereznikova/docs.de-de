---
title: Ermitteln der Dienstvorgangsdauer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 24f1bc22e088c0198ec8a8f8183611d2b43941b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="ab2ee-102">Ermitteln der Dienstvorgangsdauer</span><span class="sxs-lookup"><span data-stu-id="ab2ee-102">Determining service operation duration</span></span>
<span data-ttu-id="ab2ee-103">Wenn die analytische Ablaufverfolgung in einer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Anwendung aktiviert wird, kann die Dauer der Ausführung eines Dienstvorgangs problemlos bestimmt werden, indem das Ereignisprotokoll untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-103">If analytic tracing is enabled in a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="ab2ee-104">Dieses Thema veranschaulicht, wie die Zeitdauer bestimmt wird, die ein Dienstvorgang bis zu seinem Abschluss benötigt.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-104">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="ab2ee-105">Bestimmen der Ausführungsdauer eines Dienstvorgangs</span><span class="sxs-lookup"><span data-stu-id="ab2ee-105">Determining service operation execution duration</span></span>  
  
1.  <span data-ttu-id="ab2ee-106">Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="ab2ee-107">Wenn Sie analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** .</span><span class="sxs-lookup"><span data-stu-id="ab2ee-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="ab2ee-108">Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="ab2ee-109">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="ab2ee-110">Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-110">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3.  <span data-ttu-id="ab2ee-111">Öffnen Sie danach eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Anwendung, das ein Dienstprojekt und ein Clientprojekt, das mit dem Dienst interagiert, enthält.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-111">Next, open a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="ab2ee-112">Sie können eine solchen Anwendung erstellen, indem Sie die folgenden der [Lernprogramm für erste Schritte](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ab2ee-112">You can create such an application by following the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  <span data-ttu-id="ab2ee-113">Haben die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Beispiele, die installiert werden, öffnen Sie die [Einstieg](../../../../../docs/framework/wcf/samples/getting-started-sample.md), enthält das abgeschlossene Projekt, das im Lernprogramm erstellt.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-113">If you have the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="ab2ee-114">Führen Sie die Serveranwendung durch Drücken von **F5**.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-114">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="ab2ee-115">Führen Sie die Client-Anwendung, indem Sie mit der rechten Maustaste auf die **Client** Projekt klicken und auswählen **Debuggen**, **neue Instanz starten**.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-115">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5.  <span data-ttu-id="ab2ee-116">Aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-116">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="ab2ee-117">Suchen Sie nach Ereignissen mit der Ereignis-ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span><span class="sxs-lookup"><span data-stu-id="ab2ee-117">Look for events with Event ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span></span>  <span data-ttu-id="ab2ee-118">Anhand dieser Ereignisse können Sie sehen, welche Vorgänge abgeschlossen wurden und wie lange die Vorgänge dauerten.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-118">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="ab2ee-119">Das folgende Ereignis zeigt die Dauer eines Add-Vorgangs an.</span><span class="sxs-lookup"><span data-stu-id="ab2ee-119">The following event shows the duration of an Add operation.</span></span>  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
