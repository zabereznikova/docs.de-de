---
title: 'Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9152e0047102661664f9b158aa26f83fb1d3c25c
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten
JSON (JavaScript Object Notation) ist ein effizientes Datencodierungsformat, das einen schnellen Austausch kleiner Datenmengen zwischen Clientbrowsern und AJAX-aktivierten Webdiensten ermöglicht.  
  
 In diesem Thema wird gezeigt, wie .NET-Typobjekte mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> in JSON-codierte Daten serialisiert und Daten im JSON-Format anschließend wieder in Instanzen von .NET-Typen deserialisiert werden. Dieses Beispiel verwendet einen Datenvertrag, um die Serialisierung und die Deserialisierung eines benutzerdefinierten `Person`-Typs zu veranschaulichen.  
  
 In der Regel wird die JSON-Serialisierung und -Deserialisierung automatisch von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] vorgenommen, wenn Sie Datenvertragstypen in Dienstvorgängen verwenden, die über AJAX-aktivierte Endpunkte verfügbar gemacht werden. In manchen Fällen müssen Sie möglicherweise direkt mit JSON-Daten arbeiten. Dieses Szenario wird in diesem Thema veranschaulicht.  
  
> [!NOTE]
>  Wenn bei der Serialisierung einer ausgehenden Antwort auf dem Server ein Fehler auftritt oder wenn der Antwortvorgang aus einem anderen Grund eine Ausnahme auslöst, wird möglicherweise kein Fehler an den Client zurückgegeben.  
  
 In diesem Thema beruht auf dem [JSON-Serialisierung](../../../../docs/framework/wcf/samples/json-serialization.md) Beispiel.  
  
### <a name="to-define-the-data-contract-for-a-person"></a>So definieren Sie den Datenvertrag für eine Person  
  
1.  Definieren Sie den Datenvertrag für `Person`, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute> an die Klasse und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut an die zu serialisierenden Member anhängen. Weitere Informationen zu Datenverträgen finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a>So serialisieren Sie eine Instanz des Person-Typs in JSON  
  
1.  Erstellen Sie eine Instanz des `Person`-Typs.  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  Serialisieren Sie das `Person`-Objekt mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> in einen Speicherstream.  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  Verwenden Sie die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>-Methode, um JSON-Daten in den Stream zu schreiben.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  Zeigen Sie die JSON-Ausgabe an.  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>So deserialisieren Sie eine Instanz des Person-Typs von JSON  
  
1.  Deserialisieren Sie die JSON-codierten Daten mit der `Person`-Methode des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> in eine neue Instanz von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  Zeigen Sie die Ergebnisse an.  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a>Beispiel  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  Wie im folgenden Beispiel gezeigt, löst der JSON-Serialisierer eine Serialisierungsausnahme für Datenverträge aus, die mehrere Member mit demselben Namen besitzen:  
  
```csharp  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}

[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenständige JSON-Serialisierung.](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [Unterstützung für JSON und andere Datenübertragungsformate](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
