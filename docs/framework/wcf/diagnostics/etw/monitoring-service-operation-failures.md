---
title: "Fehler beim Überwachen von Dienstvorgängen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce62eb348cb57ce6137c58fbc50a32e829980c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="monitoring-service-operation-failures"></a><span data-ttu-id="0a794-102">Fehler beim Überwachen von Dienstvorgängen</span><span class="sxs-lookup"><span data-stu-id="0a794-102">Monitoring Service Operation Failures</span></span>
<span data-ttu-id="0a794-103">Wenn die analytische Ablaufverfolgung für eine Anwendung aktiviert ist, können Dienstfehler in der Ereignisanzeige auf einfache Weise überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="0a794-103">If analytic tracing is enabled for an application, service failures can easily be monitored in the event viewer.</span></span>  <span data-ttu-id="0a794-104">In diesem Thema wird erläutert, wie festgestellt wird, wenn ein Dienstvorgang fehlschlägt, und wie die Fehlerursache bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="0a794-104">This topic demonstrates how to determine when a service operation fails, and how to determine what caused the failure.</span></span>  
  
### <a name="determining-service-operation-failure-information"></a><span data-ttu-id="0a794-105">Bestimmen der Fehlerinformationen des Dienstvorgangs</span><span class="sxs-lookup"><span data-stu-id="0a794-105">Determining service operation failure information</span></span>  
  
1.  <span data-ttu-id="0a794-106">Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="0a794-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="0a794-107">Wenn Sie analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** .</span><span class="sxs-lookup"><span data-stu-id="0a794-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="0a794-108">Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**.</span><span class="sxs-lookup"><span data-stu-id="0a794-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="0a794-109">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="0a794-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="0a794-110">Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="0a794-110">Leave Event Viewer open so that traces can be viewed after the service operation fails.</span></span>  
  
3.  <span data-ttu-id="0a794-111">Als Nächstes öffnen Sie das Beispiel erstellt, der [Lernprogramm für erste Schritte](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Hinweis an, die Sie ausführen müssen [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] als Administrator, damit der Dienst erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a794-111">Next, open the sample created in the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Note that you must run [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] as an administrator so that the service can be created.</span></span> <span data-ttu-id="0a794-112">Haben die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Beispiele, die installiert werden, öffnen Sie die [Einstieg](../../../../../docs/framework/wcf/samples/getting-started-sample.md), enthält das abgeschlossene Projekt, das im Lernprogramm erstellt.</span><span class="sxs-lookup"><span data-stu-id="0a794-112">If you have the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="0a794-113">Fügen Sie im Serverprojekt in der Datei Program.cs die folgende Codezeile am Anfang der `Divide`-Methode in der `CalculatorService`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="0a794-113">In the Program.cs file in the Server project, add the following line of code to the start of the `Divide` method in the `CalculatorService` class:</span></span>  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  <span data-ttu-id="0a794-114">Ändern Sie in der Datei Program.cs im Clientprojekt den Wert, der Wert2 zugewiesen ist, in 0 (null):</span><span class="sxs-lookup"><span data-stu-id="0a794-114">In the Program.cs file in the Client project, change the value assigned to value2 to zero:</span></span>  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  <span data-ttu-id="0a794-115">Führen Sie die Serveranwendung ohne Debuggen durch Drücken von **STRG + F5**.</span><span class="sxs-lookup"><span data-stu-id="0a794-115">Execute the server application without debugging by pressing **Ctrl+F5**.</span></span>  
  
7.  <span data-ttu-id="0a794-116">Öffnen Sie eine Visual Studio-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="0a794-116">Open a Visual Studio command prompt.</span></span>  <span data-ttu-id="0a794-117">Navigieren Sie zum Clientverzeichnis, und führen Sie den Client über die Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="0a794-117">Navigate to the client directory and execute the client from the command line.</span></span>  
  
8.  <span data-ttu-id="0a794-118">Deaktivieren und aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="0a794-118">In Event Viewer, disable and refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="0a794-119">Suchen Sie nach einem Ereignis mit der Ereignis-ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), das den Dienstfehler beschreibt.</span><span class="sxs-lookup"><span data-stu-id="0a794-119">Look for an event with Event ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), which describes the service failure.</span></span>  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0a794-120">Ereignisse werden gepuffert, wenn sie an die Ereignisanzeige gesendet werden; das Fehlerereignis wird möglicherweise nicht sofort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0a794-120">Events are buffered when being sent to the event viewer; the failure event may not appear right away.</span></span>
