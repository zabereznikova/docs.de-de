---
title: JSON-Serialisierung
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: bb38005c02e9b3e850282d2a81c2e17143657025
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989858"
---
# <a name="json-serialization"></a>JSON-Serialisierung
Dieses Beispiel zeigt, wie mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> Daten im JSON-Format (JavaScript Object Notation) serialisiert und deserialisiert werden. Diese Serialisierungs-Engine konvertiert JSON-Daten in Instanzen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen und wieder zurück in JSON-Daten. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> unterstützt dieselben Typen wie <xref:System.Runtime.Serialization.DataContractSerializer>. Das JSON-Datenformat ist besonders beim Schreiben von Webanwendungen im Ajax-Stil (Asynchronous JavaScript and XML) nützlich. AJAX-Unterstützung in Windows Communication Foundation (WCF) ist für die Verwendung mit ASP.NET AJAX über das ScriptManager-Steuerelement optimiert. Beispiele zur Verwendung von Windows Communication Foundation (WCF) mit ASP.NET AJAX finden Sie in der [AJAX-Beispielen](ajax.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Das Beispiel verwendet einen `Person`-Datenvertrag, um die Serialisierung und Deserialisierung zu demonstrieren.  

```csharp
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

```csharp
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

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 Wenn Sie das `p2`-Objekt untersuchen, stellen Sie fest, dass die JSON-Daten ordnungsgemäß deserialisiert wurden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1. Erstellen Sie die Projektmappe JsonSerialization.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Führen Sie die dabei entstandene Konsolenanwendung aus.  
