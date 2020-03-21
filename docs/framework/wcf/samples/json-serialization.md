---
title: DataContractJsonSerializer-Beispiel
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: d3456582d73640f1802c17d7f29f4931a6f920b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144629"
---
# <a name="datacontractjsonserializer-sample"></a>DataContractJsonSerializer-Beispiel

> [!NOTE]
> Dieses Beispiel <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>ist für . Für die meisten Szenarien, die die Serialisierung und Deserialisierung von JSON beinhalten, empfehlen wir die APIs im [Namespace System.Text.Json](../../../standard/serialization/system-text-json-overview.md).

<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> unterstützt dieselben Typen wie <xref:System.Runtime.Serialization.DataContractSerializer>. Das JSON-Datenformat ist besonders beim Schreiben von Webanwendungen im Ajax-Stil (Asynchronous JavaScript and XML) nützlich. Die AJAX-Unterstützung in Windows Communication Foundation (WCF) ist für die Verwendung mit ASP.NET AJAX über das ScriptManager-Steuerelement optimiert. Beispiele für die Verwendung von Windows Communication Foundation (WCF) mit ASP.NET AJAX finden Sie in den [AJAX-Beispielen](ajax.md).  
  
Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
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
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1. Erstellen Sie die Lösung JsonSerialization.sln, wie unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)beschrieben.  
  
2. Führen Sie die dabei entstandene Konsolenanwendung aus.  
