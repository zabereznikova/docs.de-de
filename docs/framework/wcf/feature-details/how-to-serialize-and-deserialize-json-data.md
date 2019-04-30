---
title: 'Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 7edce66a23021fa03a6f98b3b847a5b671c17124
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972990"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten
JSON (JavaScript Object Notation) ist ein effizientes Datencodierungsformat, das einen schnellen Austausch kleiner Datenmengen zwischen Clientbrowsern und AJAX-aktivierten Webdiensten ermöglicht.  
  
 In diesem Artikel wird veranschaulicht, wie .NET Type-Objekten in JSON-codierte Daten serialisiert und Daten im JSON-Format anschließend wieder in Instanzen von .NET-Typen deserialisiert werden. Dieses Beispiel verwendet einen Datenvertrag, um Serialisierung und Deserialisierung von einer benutzerdefinierten veranschaulichen `Person` Typ und verwendet <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
 Normalerweise werden JSON-Serialisierung und Deserialisierung automatisch von Windows Communication Foundation (WCF) behandelt, wenn Sie Datenvertragstypen in Dienstvorgängen verwenden, die über AJAX-aktivierte Endpunkte verfügbar gemacht werden. In einigen Fällen müssen Sie jedoch direkt mit JSON-Daten arbeiten.   
  
> [!NOTE]
>  Wenn ein Fehler während der Serialisierung einer ausgehenden Antwort auf dem Server oder einem anderen Grund auftritt, wird möglicherweise nicht an den Client als Fehler zurückgegeben.  
  
 Dieser Artikel basiert auf der [JSON-Serialisierung](../samples/json-serialization.md) Beispiel.  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a>Definiert den Datenvertrag für einen Typ "Person" 
  
1. Definieren Sie den Datenvertrag für `Person`, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute> an die Klasse und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut an die zu serialisierenden Member anhängen. Weitere Informationen zu Datenverträgen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).  
  
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
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a>So serialisieren Sie eine Instanz des Person-Typs in JSON  
  
1. Erstellen Sie eine Instanz des `Person`-Typs.  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2. Serialisieren der `Person` Objekt in einen Speicherdatenstrom mit den <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3. Verwenden Sie die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>-Methode, um JSON-Daten in den Stream zu schreiben.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4. Zeigen Sie die JSON-Ausgabe an.  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a>So deserialisieren Sie eine Instanz des Person-Typs von JSON  
  
1. Deserialisieren Sie die JSON-codierten Daten mit der `Person`-Methode des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> in eine neue Instanz von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2. Zeigen Sie die Ergebnisse an.  
  
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

- [Eigenständige JSON-Serialisierung](stand-alone-json-serialization.md)
- [Unterstützung für JSON und andere datenübertragungs-Formate](support-for-json-and-other-data-transfer-formats.md)
