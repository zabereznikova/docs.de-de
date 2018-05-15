---
title: Konfigurationskanalfactory
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: fc3a564128e520133c2404a82438e692b1381875
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="89c65-102">Konfigurationskanalfactory</span><span class="sxs-lookup"><span data-stu-id="89c65-102">Configuration Channel Factory</span></span>
<span data-ttu-id="89c65-103">In diesem Beispiel wird die Verwendung von <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> behandelt.</span><span class="sxs-lookup"><span data-stu-id="89c65-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="89c65-104">Die <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> ermöglicht die zentrale Verwaltung der WCF-Client-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="89c65-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="89c65-105">Dies kann auch in Szenarien nützlich sein, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="89c65-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="89c65-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="89c65-106">Demonstrates</span></span>  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a><span data-ttu-id="89c65-107">Diskussion</span><span class="sxs-lookup"><span data-stu-id="89c65-107">Discussion</span></span>  
 <span data-ttu-id="89c65-108">In diesem Beispiel wird gezeigt, wie eine bestimmte Konfigurationsdatei mit <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zu einer Clientanwendung hinzugefügt wird, ohne die standardmäßige Anwendungskonfigurationsdatei verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="89c65-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>  
  
 <span data-ttu-id="89c65-109">Das Beispiel umfasst zwei Projekte.</span><span class="sxs-lookup"><span data-stu-id="89c65-109">The sample consists of two projects.</span></span> <span data-ttu-id="89c65-110">Das erste Projekt ist ein einfacher Dienst, der auf Nachrichten von den Clients antwortet.</span><span class="sxs-lookup"><span data-stu-id="89c65-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="89c65-111">Das zweite Projekt ist eine Clientanwendung, die für die Konfigurationsdatei Test.config mithilfe einer <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zwei <xref:System.Configuration.ExeConfigurationFileMap>-Objekte erstellt und diese für die Kommunikation mit dem Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="89c65-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="89c65-112">Beide Clients verwenden die in Test.config angegebene Konfiguration für die Kommunikation mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="89c65-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>  
  
 <span data-ttu-id="89c65-113">Der folgende Code fügt einer Clientanwendung eine benutzerdefinierte Konfigurationsdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="89c65-113">The following code adds a custom configuration file to a client application.</span></span>  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="89c65-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="89c65-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="89c65-115">Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="89c65-115">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="89c65-116">Mit der rechten Maustaste in der Projektmappe configurationchannelfactory (2 Projekte), und wählen Sie dann **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="89c65-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="89c65-117">In **allgemeine Eigenschaften**Option **Startprojekt**, und klicken Sie dann auf **mehrere Startprojekte**.</span><span class="sxs-lookup"><span data-stu-id="89c65-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>  
  
4.  <span data-ttu-id="89c65-118">Verschieben der **Service** Projekt am Anfang der Liste mit den **Aktion "Start"**, und verschieben Sie dann die **Client** nach dem Projekt die **Dienst**-Projekt auch mit der **Aktion "Start"**, sodass die **Client** Projekt ausgeführt, nachdem die **Service** Projekt.</span><span class="sxs-lookup"><span data-stu-id="89c65-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>  
  
5.  <span data-ttu-id="89c65-119">Klicken Sie auf **OK**, und drücken Sie dann F5 (oder STRG + F5), um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="89c65-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="89c65-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="89c65-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="89c65-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="89c65-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="89c65-122">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="89c65-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="89c65-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="89c65-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
