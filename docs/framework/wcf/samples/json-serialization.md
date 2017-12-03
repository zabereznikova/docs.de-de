---
title: JSON-Serialisierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 706cea8ed07fae680987e58b118b0a87951a059b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="json-serialization"></a>JSON-Serialisierung
Dieses Beispiel zeigt, wie mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> Daten im JSON-Format (JavaScript Object Notation) serialisiert und deserialisiert werden. Dieses Serialisierungsmodul konvertiert JSON-Daten in Instanzen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen und wieder zurück in JSON-Daten. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> unterstützt dieselben Typen wie <xref:System.Runtime.Serialization.DataContractSerializer>. Das JSON-Datenformat ist besonders beim Schreiben von Webanwendungen im Ajax-Stil (Asynchronous JavaScript and XML) nützlich. Die AJAX-Unterstützung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist zur Verwendung mit ASP.NET AJAX über das ScriptManager-Steuerelement optimiert. Beispiele für die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mit ASP.NET AJAX finden Sie unter der [AJAX-Beispielen](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Das Beispiel verwendet einen `Person`-Datenvertrag, um die Serialisierung und Deserialisierung zu demonstrieren.  
  
```  
[DataContract]  
    class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
```  
  
 Zum Serialisieren einer Instanz vom Typ `Person` zu JSON erstellen Sie zuerst das <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und schreiben dann mit der `WriteObject`-Methode JSON-Daten in einen Stream.  
  
```  
Person p = new Person();  
//Set up Person object...  
MemoryStream stream1 = new MemoryStream();  
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
ser.WriteObject(stream1, p);  
```  
  
 Der Arbeitsspeicherstream enthält gültige JSON-Daten.  
  
```json  
{"age":42,"name":"John"}  
```  
  
 Das Beispiel zeigt das Deserialisieren von JSON-Daten in ein Objekt. Anschließend spulen Sie den Stream zurück und rufen `ReadObject` auf.  
  
```  
Person p2 = (Person)ser.ReadObject(stream1);  
```  
  
 Wenn Sie das `p2`-Objekt untersuchen, stellen Sie fest, dass die JSON-Daten ordnungsgemäß deserialisiert wurden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Erstellen Sie die Projektmappe JsonSerialization.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Führen Sie die dabei entstandene Konsolenanwendung aus.  
  
## <a name="see-also"></a>Siehe auch
