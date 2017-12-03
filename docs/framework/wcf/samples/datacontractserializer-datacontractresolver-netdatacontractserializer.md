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
ms.openlocfilehash: 91d3293b1229434462dd0f6b31bc1de2df925a40
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a>Bereitstellen der Funktionen für NetDataContractSerializer mit DataContractSerializer und DataContractResolver
In diesem Beispiel wird veranschaulicht, wie die Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> mit einem entsprechenden <xref:System.Runtime.Serialization.DataContractResolver> die gleiche Funktionalität wie der <xref:System.Runtime.Serialization.NetDataContractSerializer> bereitstellt. In diesem Beispiel wird gezeigt, wie der entsprechende <xref:System.Runtime.Serialization.DataContractResolver> erstellt und dem <xref:System.Runtime.Serialization.DataContractSerializer> hinzugefügt wird.  
  
## <a name="sample-details"></a>Beispieldetails  
 <xref:System.Runtime.Serialization.NetDataContractSerializer> unterscheidet sich von <xref:System.Runtime.Serialization.DataContractSerializer> in einem wichtigen Punkt: <xref:System.Runtime.Serialization.NetDataContractSerializer> enthält im Gegensatz zu <xref:System.Runtime.Serialization.DataContractSerializer> CLR-Typinformationen im serialisierten XML. <xref:System.Runtime.Serialization.NetDataContractSerializer> kann daher nur verwendet werden, wenn sowohl der Endpunkt für die Serialisierung als auch der Endpunkt für die Deserialisierung den gleichen CLR-Typ aufweisen. Es wird jedoch empfohlen, <xref:System.Runtime.Serialization.DataContractSerializer> zu verwenden, da er eine höhere Leistung bietet als <xref:System.Runtime.Serialization.NetDataContractSerializer>. Sie können die Informationen ändern, die in <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert sind, indem Sie einen <xref:System.Runtime.Serialization.DataContractResolver> hinzuzufügen.  
  
 Dieses Beispiel besteht aus zwei Projekten. Das erste Projekt verwendet <xref:System.Runtime.Serialization.NetDataContractSerializer> für das Serialisieren eines Objekts. Das zweite Projekt verwendet <xref:System.Runtime.Serialization.DataContractSerializer> mit einem <xref:System.Runtime.Serialization.DataContractResolver>, um die gleiche Funktionalität wie das erste Projekt bereitzustellen.  
  
 Im folgenden Codebeispiel wird die Implementierung von einem benutzerdefinierten <xref:System.Runtime.Serialization.DataContractResolver> mit dem Namen `MyDataContractResolver` veranschaulicht, der dem <xref:System.Runtime.Serialization.DataContractSerializer> im DCSwithDCR-Projekt hinzugefügt wird.  
  
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
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei DCRSample.sln.  
  
2.  Die Projektmappendatei Maustaste und wählen Sie **Eigenschaften**.  
  
3.  In der **-Eigenschaftenseiten** Dialogfeld unter **allgemeine Eigenschaften**, **Startprojekt**Option **mehrere Startprojekte:**.  
  
4.  Neben den **DCSwithDCR** -Projekt, wählen **starten** aus der **Aktion** Dropdownliste.  
  
5.  Neben den **NetDCS** -Projekt, wählen **starten** aus der **Aktion** Dropdownliste.  
  
6.  Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
7.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
8.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
## <a name="see-also"></a>Siehe auch
