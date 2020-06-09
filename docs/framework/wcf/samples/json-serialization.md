---
title: DataContractJsonSerializer-Beispiel
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 4aa0ee679ae424251000b14abfbacf0590a6ccd3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592020"
---
# <a name="datacontractjsonserializer-sample"></a>DataContractJsonSerializer-Beispiel

> [!NOTE]
> Dieses Beispiel ist für <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> . In den meisten Szenarien, in denen JSON serialisiert und deserialisiert wird, empfehlen wir die APIs im [System. Text. Json-Namespace](../../../standard/serialization/system-text-json-overview.md).

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
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1. Erstellen Sie die Projektmappendatei "jsonSerialization. sln", wie unter [Erstellen der Windows Communication Foundation Beispiele](building-the-samples.md)beschrieben.  
  
2. Führen Sie die dabei entstandene Konsolenanwendung aus.  
