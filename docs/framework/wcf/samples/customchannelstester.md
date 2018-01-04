---
title: CustomChannelsTester
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92de7f168ce323a0d84975863564389ff389d680
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="customchannelstester"></a><span data-ttu-id="2878d-102">CustomChannelsTester</span><span class="sxs-lookup"><span data-stu-id="2878d-102">CustomChannelsTester</span></span>
<span data-ttu-id="2878d-103">Der `CustomChannelsTester` ist ein Tool, das Sie zum Testen Ihrer benutzerdefinierten Channelimplementierungen mit einem Satz vordefinierter Dienstverträge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2878d-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="2878d-104">Sie können einen Satz von Dienstverträgen auswählen und diesen mithilfe einer XML-Datei an das Tool übergeben.</span><span class="sxs-lookup"><span data-stu-id="2878d-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="2878d-105">Anschließend generiert das Tool den Dienst und den Client, die die benutzerdefinierten Channelimplementierungen während des Nachrichtenaustauschs ausführen.</span><span class="sxs-lookup"><span data-stu-id="2878d-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="2878d-106">So erstellen Sie das Tool</span><span class="sxs-lookup"><span data-stu-id="2878d-106">To build the tool</span></span>  
  
1.  <span data-ttu-id="2878d-107">Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2878d-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="2878d-108">Während der Erstellung der Projektmappe werden drei Dateien generiert: "CustomChannelsTester.exe", "TestSpec.xml" und "SampleRun.cmd".</span><span class="sxs-lookup"><span data-stu-id="2878d-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="2878d-109">Die Datei "samplerun.cmd" hat eine Beispielbefehlszeile, die zeigt, wie Sie dieses Tool zum Testen verwenden die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2878d-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="2878d-110">So führen Sie das Tool aus</span><span class="sxs-lookup"><span data-stu-id="2878d-110">To run the tool</span></span>  
  
-   <span data-ttu-id="2878d-111">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="2878d-111">At the command prompt type the following command:</span></span>  
  
    ```  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="2878d-112">Die Verwendung der `/binding`-Option ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2878d-112">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="2878d-113">`/dll` ist erforderlich, wenn die "Bindung" keine vom System und von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bereitgestellte Bindung ist.</span><span class="sxs-lookup"><span data-stu-id="2878d-113">`/dll` is required if "binding" is not a system-provided binding provided by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
     <span data-ttu-id="2878d-114">`/testspec` ist optional.</span><span class="sxs-lookup"><span data-stu-id="2878d-114">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="2878d-115">Auf diese Weise werden Server und Clients auf der Grundlage der Testspezifikationen und der Bindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="2878d-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="2878d-116">Der Client und der Server werden ausgeführt und die Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2878d-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="2878d-117">Folgendes ist der Beispiel-XML-Code für die Beschreibung der Testspezifikationen (testspec.xml):</span><span class="sxs-lookup"><span data-stu-id="2878d-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the CLient. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2878d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2878d-118">See Also</span></span>
