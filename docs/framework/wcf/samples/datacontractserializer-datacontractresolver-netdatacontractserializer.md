---
title: "Bereitstellen der Funktionen für NetDataContractSerializer mit DataContractSerializer und DataContractResolver"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5477f11b5bc00ff4816b3fac8d61b254ebaf5ba0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="f3ade-102">Bereitstellen der Funktionen für NetDataContractSerializer mit DataContractSerializer und DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="f3ade-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="f3ade-103">In diesem Beispiel wird veranschaulicht, wie die Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> mit einem entsprechenden <xref:System.Runtime.Serialization.DataContractResolver> die gleiche Funktionalität wie der <xref:System.Runtime.Serialization.NetDataContractSerializer> bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f3ade-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="f3ade-104">In diesem Beispiel wird gezeigt, wie der entsprechende <xref:System.Runtime.Serialization.DataContractResolver> erstellt und dem <xref:System.Runtime.Serialization.DataContractSerializer> hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f3ade-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="f3ade-105">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="f3ade-105">Sample details</span></span>  
 <span data-ttu-id="f3ade-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> unterscheidet sich von <xref:System.Runtime.Serialization.DataContractSerializer> in einem wichtigen Punkt: <xref:System.Runtime.Serialization.NetDataContractSerializer> enthält im Gegensatz zu <xref:System.Runtime.Serialization.DataContractSerializer> CLR-Typinformationen im serialisierten XML.</span><span class="sxs-lookup"><span data-stu-id="f3ade-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="f3ade-107"><xref:System.Runtime.Serialization.NetDataContractSerializer> kann daher nur verwendet werden, wenn sowohl der Endpunkt für die Serialisierung als auch der Endpunkt für die Deserialisierung den gleichen CLR-Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f3ade-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="f3ade-108">Es wird jedoch empfohlen, <xref:System.Runtime.Serialization.DataContractSerializer> zu verwenden, da er eine höhere Leistung bietet als <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f3ade-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="f3ade-109">Sie können die Informationen ändern, die in <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert sind, indem Sie einen <xref:System.Runtime.Serialization.DataContractResolver> hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3ade-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>  
  
 <span data-ttu-id="f3ade-110">Dieses Beispiel besteht aus zwei Projekten.</span><span class="sxs-lookup"><span data-stu-id="f3ade-110">This sample consists of two projects.</span></span> <span data-ttu-id="f3ade-111">Das erste Projekt verwendet <xref:System.Runtime.Serialization.NetDataContractSerializer> für das Serialisieren eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="f3ade-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="f3ade-112">Das zweite Projekt verwendet <xref:System.Runtime.Serialization.DataContractSerializer> mit einem <xref:System.Runtime.Serialization.DataContractResolver>, um die gleiche Funktionalität wie das erste Projekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f3ade-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>  
  
 <span data-ttu-id="f3ade-113">Im folgenden Codebeispiel wird die Implementierung von einem benutzerdefinierten <xref:System.Runtime.Serialization.DataContractResolver> mit dem Namen `MyDataContractResolver` veranschaulicht, der dem <xref:System.Runtime.Serialization.DataContractSerializer> im DCSwithDCR-Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f3ade-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>  
  
```  
class MyDataContractResolver : DataContractResolver  
{  
    private XmlDictionary dictionary = new XmlDictionary();  
  
    public MyDataContractResolver()  
    {  
    }  
  
    // Used at deserialization  
    // Allows users to map xsi:type name to any Type   
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        if (type == null)  
        {  
            type = Type.GetType(typeName + ", " + typeNamespace);  
        }  
        return type;  
    }  
  
    // Used at serialization  
    // Maps any Type to a new xsi:type representation  
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);  
        if (typeName == null || typeNamespace == null)  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add(dataContractType.FullName);  
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);  
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f3ade-114">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3ade-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="f3ade-115">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei DCRSample.sln.</span><span class="sxs-lookup"><span data-stu-id="f3ade-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the DCRSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f3ade-116">Die Projektmappendatei Maustaste und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f3ade-116">Right-click the solution file and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="f3ade-117">In der **-Eigenschaftenseiten** Dialogfeld unter **allgemeine Eigenschaften**, **Startprojekt**Option **mehrere Startprojekte:**.</span><span class="sxs-lookup"><span data-stu-id="f3ade-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>  
  
4.  <span data-ttu-id="f3ade-118">Neben den **DCSwithDCR** -Projekt, wählen **starten** aus der **Aktion** Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="f3ade-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>  
  
5.  <span data-ttu-id="f3ade-119">Neben den **NetDCS** -Projekt, wählen **starten** aus der **Aktion** Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="f3ade-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>  
  
6.  <span data-ttu-id="f3ade-120">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f3ade-120">Click **OK** to close the dialog.</span></span>  
  
7.  <span data-ttu-id="f3ade-121">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3ade-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
8.  <span data-ttu-id="f3ade-122">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f3ade-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f3ade-123">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f3ade-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f3ade-124">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f3ade-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f3ade-125">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f3ade-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f3ade-126">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f3ade-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
## <a name="see-also"></a><span data-ttu-id="f3ade-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3ade-127">See Also</span></span>
