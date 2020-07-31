---
title: 'Vorgehensweise: Protokollinformationen über Dienste'
description: In diesem Artikel erhalten Sie Informationen zum Protokollieren von Informationen zu Diensten. Legen Sie die AutoLog-Eigenschaft fest, wenn Sie möchten, dass Ihr Windows-Dienstprojekt mit dem Anwendungsereignisprotokoll interagiert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
author: ghogen
ms.openlocfilehash: 6ebce5464dc25ba4101b3898ee791714f8efc5d6
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925747"
---
# <a name="how-to-log-information-about-services"></a><span data-ttu-id="d9d95-104">Vorgehensweise: Protokollinformationen über Dienste</span><span class="sxs-lookup"><span data-stu-id="d9d95-104">How to: Log Information About Services</span></span>
<span data-ttu-id="d9d95-105">Standardmäßig können alle Windows-Dienst-Projekte auf das Anwendungsereignisprotokoll zugreifen und Informationen sowie Ausnahmen in das Protokoll schreiben.</span><span class="sxs-lookup"><span data-stu-id="d9d95-105">By default, all Windows Service projects have the ability to interact with the Application event log and write information and exceptions to it.</span></span> <span data-ttu-id="d9d95-106">Sie geben über die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft an, ob Sie diese Funktionalität in Ihrer Anwendung nutzen möchten.</span><span class="sxs-lookup"><span data-stu-id="d9d95-106">You use the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to indicate whether you want this functionality in your application.</span></span> <span data-ttu-id="d9d95-107">Standardmäßig ist die Protokollierung für jeden Dienst aktiviert, den Sie mit den Projektvorlagen für Windows-Dienste erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9d95-107">By default, logging is turned on for any service you create with the Windows Service project template.</span></span> <span data-ttu-id="d9d95-108">Sie können eine statische Form der <xref:System.Diagnostics.EventLog> -Klasse verwenden, um Dienstinformationen in ein Protokoll zu schreiben, ohne dass Sie eine Instanz von einer <xref:System.Diagnostics.EventLog> -Komponente erstellen oder eine Quelle manuell registrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="d9d95-108">You can use a static form of the <xref:System.Diagnostics.EventLog> class to write service information to a log without having to create an instance of an <xref:System.Diagnostics.EventLog> component or manually register a source.</span></span>  
  
 <span data-ttu-id="d9d95-109">Das Installationsprogramm für Ihren Dienst registriert jeden Dienst in Ihrem Projekt automatisch als gültige Quelle von Ereignissen für das Anwendungsprotokoll auf dem Computer, auf dem der Dienst installiert ist, wenn die Protokollierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d9d95-109">The installer for your service automatically registers each service in your project as a valid source of events with the Application log on the computer where the service is installed, when logging is turned on.</span></span> <span data-ttu-id="d9d95-110">Der Dienst protokolliert jedes Mal Informationen, wenn er gestartet, beendet, angehalten, fortgesetzt, installiert oder deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="d9d95-110">The service logs information each time the service is started, stopped, paused, resumed, installed, or uninstalled.</span></span> <span data-ttu-id="d9d95-111">Der Dienst protokolliert auch alle auftretenden Fehler.</span><span class="sxs-lookup"><span data-stu-id="d9d95-111">It also logs any failures that occur.</span></span> <span data-ttu-id="d9d95-112">Wird das Standardverhalten verwendet, müssen Sie keinen Code schreiben, damit Einträge in das Protokoll geschrieben werden. Dies wird vom Dienst automatisch erledigt.</span><span class="sxs-lookup"><span data-stu-id="d9d95-112">You do not need to write any code to write entries to the log when using the default behavior; the service handles this for you automatically.</span></span>  
  
 <span data-ttu-id="d9d95-113">Wenn Sie möchten, dass nicht in das Anwendungsprotokoll, sondern in ein anderes Ereignisprotokoll geschrieben werden soll, müssen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft auf `false`festlegen, im Code Ihres Diensts Ihr eigenes Ereignisprotokoll erstellen und den Dienst als eine gültige Quelle für Einträge für dieses Protokoll registrieren.</span><span class="sxs-lookup"><span data-stu-id="d9d95-113">If you want to write to an event log other than the Application log, you must set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`, create your own custom event log within your services code, and register your service as a valid source of entries for that log.</span></span> <span data-ttu-id="d9d95-114">Danach müssen Sie Code schreiben, mit dem jedes Mal dann Einträge im Protokoll festgehalten werden, wenn eine Aktion auftritt, an der Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="d9d95-114">You must then write code to record entries to the log whenever an action you're interested in occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9d95-115">Wenn Sie ein benutzerdefiniertes Ereignisprotokoll verwenden und Ihren Dienst so konfigurieren, dass er in dieses Protokoll schreibt, dürfen Sie nicht versuchen, auf das Ereignisprotokoll zuzugreifen, bevor die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> -Eigenschaft des Diensts im Code festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="d9d95-115">If you use a custom event log and configure your service application to write to it, you must not attempt to access the event log before setting the service's <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property in your code.</span></span> <span data-ttu-id="d9d95-116">Der Wert dieser Eigenschaft ist für das Ereignisprotokoll erforderlich, damit Ihr Dienst als gültige Quelle für Ereignisse registriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9d95-116">The event log needs this property's value to register your service as a valid source of events.</span></span>  
  
### <a name="to-enable-default-event-logging-for-your-service"></a><span data-ttu-id="d9d95-117">So aktivieren Sie die Standardereignisprotokollierung für Ihren Dienst</span><span class="sxs-lookup"><span data-stu-id="d9d95-117">To enable default event logging for your service</span></span>  
  
- <span data-ttu-id="d9d95-118">Legen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft für Ihre Komponente auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="d9d95-118">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `true`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d9d95-119">Standardmäßig ist diese Eigenschaft auf `true`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9d95-119">By default, this property is set to `true`.</span></span> <span data-ttu-id="d9d95-120">Sie müssen dies nur dann explizit festlegen, wenn Sie eine komplexere Verarbeitung erstellen, etwa Auswerten einer Bedingung und dann Festlegen der <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft anhand des Ergebnisses dieser Bedingung.</span><span class="sxs-lookup"><span data-stu-id="d9d95-120">You do not need to set this explicitly unless you are building more complex processing, such as evaluating a condition and then setting the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property based on the result of that condition.</span></span>  
  
### <a name="to-disable-event-logging-for-your-service"></a><span data-ttu-id="d9d95-121">So deaktivieren Sie die Ereignisprotokollierung für Ihren Dienst</span><span class="sxs-lookup"><span data-stu-id="d9d95-121">To disable event logging for your service</span></span>  
  
- <span data-ttu-id="d9d95-122">Legen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft für Ihre Komponente auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="d9d95-122">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `false`.</span></span>  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a><span data-ttu-id="d9d95-123">So richten Sie die Protokollierung in eine benutzerdefinierte Protokolldatei ein</span><span class="sxs-lookup"><span data-stu-id="d9d95-123">To set up logging to a custom log</span></span>  
  
1. <span data-ttu-id="d9d95-124">Legen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="d9d95-124">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d9d95-125">Sie müssen <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> auf „false“ festlegen, damit ein benutzerdefiniertes Protokoll verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9d95-125">You must set <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> to false in order to use a custom log.</span></span>  
  
2. <span data-ttu-id="d9d95-126">Richten Sie in Ihrer Windows-Dienst-Anwendung eine Instanz einer <xref:System.Diagnostics.EventLog> -Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="d9d95-126">Set up an instance of an <xref:System.Diagnostics.EventLog> component in your Windows Service application.</span></span>  
  
3. <span data-ttu-id="d9d95-127">Erstellen Sie ein benutzerdefiniertes Protokoll, indem Sie die <xref:System.Diagnostics.EventLog.CreateEventSource%2A> -Methode aufrufen sowie die Quellzeichenfolge und den Namen der Protokolldatei angeben, die erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9d95-127">Create a custom log by calling the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method and specifying the source string and the name of the log file you want to create.</span></span>  
  
4. <span data-ttu-id="d9d95-128">Legen Sie die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft für die <xref:System.Diagnostics.EventLog> -Komponenteninstanz auf die Quellzeichenfolge fest, die Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d9d95-128">Set the <xref:System.Diagnostics.EventLog.Source%2A> property on the <xref:System.Diagnostics.EventLog> component instance to the source string you created in step 3.</span></span>  
  
5. <span data-ttu-id="d9d95-129">Schreiben Sie die Einträge, indem Sie auf die <xref:System.Diagnostics.EventLog.WriteEntry%2A> -Methode der <xref:System.Diagnostics.EventLog> -Komponenteninstanz zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d9d95-129">Write your entries by accessing the <xref:System.Diagnostics.EventLog.WriteEntry%2A> method on the <xref:System.Diagnostics.EventLog> component instance.</span></span>  
  
     <span data-ttu-id="d9d95-130">Im folgenden Code wird veranschaulicht, wie Sie Protokollierung in ein benutzerdefiniertes Protokoll einrichten.</span><span class="sxs-lookup"><span data-stu-id="d9d95-130">The following code shows how to set up logging to a custom log.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d9d95-131">In diesem Codebeispiel wird eine Instanz einer <xref:System.Diagnostics.EventLog> -Komponente mit `eventLog1` benannt (`EventLog1` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d9d95-131">In this code example, an instance of an <xref:System.Diagnostics.EventLog> component is named `eventLog1` (`EventLog1` in Visual Basic).</span></span> <span data-ttu-id="d9d95-132">Wenn Sie in Schritt 2 eine Instanz mit einem anderen Namen erstellt haben, ändern Sie den Code entsprechend.</span><span class="sxs-lookup"><span data-stu-id="d9d95-132">If you created an instance with another name in step 2, change the code accordingly.</span></span>  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="d9d95-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9d95-133">See also</span></span>

- [<span data-ttu-id="d9d95-134">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="d9d95-134">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
