---
title: Konfigurationskanalfactory
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: bebdd7e5913fd3bbc1ab88d32e6612b9bc951852
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241147"
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="eaada-102">Konfigurationskanalfactory</span><span class="sxs-lookup"><span data-stu-id="eaada-102">Configuration Channel Factory</span></span>

<span data-ttu-id="eaada-103">In diesem Beispiel wird die Verwendung von <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> behandelt.</span><span class="sxs-lookup"><span data-stu-id="eaada-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="eaada-104">Die <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> ermöglicht die zentrale Verwaltung der WCF-Client Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eaada-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="eaada-105">Dies kann auch in Szenarien nützlich sein, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="eaada-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="eaada-106">Zeigt</span><span class="sxs-lookup"><span data-stu-id="eaada-106">Demonstrates</span></span>

 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a><span data-ttu-id="eaada-107">Diskussion</span><span class="sxs-lookup"><span data-stu-id="eaada-107">Discussion</span></span>

 <span data-ttu-id="eaada-108">In diesem Beispiel wird gezeigt, wie eine bestimmte Konfigurationsdatei mit <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zu einer Clientanwendung hinzugefügt wird, ohne die standardmäßige Anwendungskonfigurationsdatei verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="eaada-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>

 <span data-ttu-id="eaada-109">Das Beispiel umfasst zwei Projekte.</span><span class="sxs-lookup"><span data-stu-id="eaada-109">The sample consists of two projects.</span></span> <span data-ttu-id="eaada-110">Das erste Projekt ist ein einfacher Dienst, der auf Nachrichten von den Clients antwortet.</span><span class="sxs-lookup"><span data-stu-id="eaada-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="eaada-111">Das zweite Projekt ist eine Clientanwendung, die für die Konfigurationsdatei Test.config mithilfe einer <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zwei <xref:System.Configuration.ExeConfigurationFileMap>-Objekte erstellt und diese für die Kommunikation mit dem Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="eaada-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="eaada-112">Beide Clients verwenden die in Test.config angegebene Konfiguration für die Kommunikation mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="eaada-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>

 <span data-ttu-id="eaada-113">Der folgende Code fügt einer Clientanwendung eine benutzerdefinierte Konfigurationsdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="eaada-113">The following code adds a custom configuration file to a client application.</span></span>

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="eaada-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="eaada-114">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="eaada-115">Öffnen Sie Visual Studio 2012 mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="eaada-115">Open Visual Studio 2012 with administrator privileges.</span></span>

2. <span data-ttu-id="eaada-116">Klicken Sie mit der rechten Maustaste auf die Lösung ConfigurationChannelFactory (2 Projekte), und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="eaada-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>

3. <span data-ttu-id="eaada-117">Wählen Sie unter **Allgemeine Eigenschaften** die Option **Startprojekt** aus, und klicken Sie dann auf **mehrere Start Projekte**.</span><span class="sxs-lookup"><span data-stu-id="eaada-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>

4. <span data-ttu-id="eaada-118">Verschieben Sie das **Dienst** Projekt an den Anfang der Liste mit der **Aktion "Start"**, und verschieben Sie das **Client** Projekt nach dem **Dienst** Projekt, auch mit der **Aktion "Start"**, damit das **Client** Projekt nach dem **Dienst** Projekt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eaada-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>

5. <span data-ttu-id="eaada-119">Klicken Sie auf **OK**, und drücken Sie dann F5 (oder STRG + F5), um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eaada-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eaada-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="eaada-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eaada-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="eaada-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="eaada-122">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eaada-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eaada-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="eaada-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
