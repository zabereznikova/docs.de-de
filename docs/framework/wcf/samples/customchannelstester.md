---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: c23bd3eddd49972b7083347fed88d4e70707ae58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183809"
---
# <a name="customchannelstester"></a><span data-ttu-id="908ba-102">CustomChannelsTester</span><span class="sxs-lookup"><span data-stu-id="908ba-102">CustomChannelsTester</span></span>
<span data-ttu-id="908ba-103">Der `CustomChannelsTester` ist ein Tool, das Sie zum Testen Ihrer benutzerdefinierten Channelimplementierungen mit einem Satz vordefinierter Dienstverträge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="908ba-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="908ba-104">Sie können einen Satz von Dienstverträgen auswählen und diesen mithilfe einer XML-Datei an das Tool übergeben.</span><span class="sxs-lookup"><span data-stu-id="908ba-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="908ba-105">Anschließend generiert das Tool den Dienst und den Client, die die benutzerdefinierten Channelimplementierungen während des Nachrichtenaustauschs ausführen.</span><span class="sxs-lookup"><span data-stu-id="908ba-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="908ba-106">So erstellen Sie das Tool</span><span class="sxs-lookup"><span data-stu-id="908ba-106">To build the tool</span></span>  
  
1. <span data-ttu-id="908ba-107">Um die Lösung zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="908ba-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="908ba-108">Während der Erstellung der Projektmappe werden drei Dateien generiert: "CustomChannelsTester.exe", "TestSpec.xml" und "SampleRun.cmd".</span><span class="sxs-lookup"><span data-stu-id="908ba-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="908ba-109">Die Datei SampleRun.cmd verfügt über eine Beispielbefehlszeile, die zeigt, wie Sie dieses Tool zum Testen des [Transport: UDP-Beispiels](../../../../docs/framework/wcf/samples/transport-udp.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="908ba-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="908ba-110">So führen Sie das Tool aus</span><span class="sxs-lookup"><span data-stu-id="908ba-110">To run the tool</span></span>  
  
- <span data-ttu-id="908ba-111">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="908ba-111">At the command prompt type the following command:</span></span>  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="908ba-112">Die Verwendung der `/binding`-Option ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="908ba-112">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="908ba-113">`/dll`ist erforderlich, wenn "Binding" keine vom System bereitgestellte Bindung von Windows Communication Foundation (WCF) ist.</span><span class="sxs-lookup"><span data-stu-id="908ba-113">`/dll` is required if "binding" is not a system-provided binding provided by Windows Communication Foundation (WCF).</span></span>  
  
     <span data-ttu-id="908ba-114">`/testspec` ist optional.</span><span class="sxs-lookup"><span data-stu-id="908ba-114">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="908ba-115">Auf diese Weise werden Server und Clients auf der Grundlage der Testspezifikationen und der Bindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="908ba-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="908ba-116">Der Client und der Server werden ausgeführt und die Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="908ba-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="908ba-117">Folgendes ist der Beispiel-XML-Code für die Beschreibung der Testspezifikationen (testspec.xml):</span><span class="sxs-lookup"><span data-stu-id="908ba-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
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
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
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
