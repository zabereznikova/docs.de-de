---
title: 'Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 0bebdbb3d74d58db093c4ec1e0e88138c7080335
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947893"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten
JSON (JavaScript Object Notation) ist ein effizientes Datencodierungsformat, das einen schnellen Austausch kleiner Datenmengen zwischen Clientbrowsern und AJAX-aktivierten Webdiensten ermöglicht.  
  
 In diesem Artikel wird veranschaulicht, wie .net-Typobjekte in JSON-codierte Daten serialisiert und anschließend Daten im JSON-Format wieder in Instanzen von .NET-Typen deserialisiert werden. In diesem Beispiel wird ein Datenvertrag verwendet, um die Serialisierung und Deserialisierung eines Benutzer `Person` definierten Typs und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>die Verwendung von zu veranschaulichen.  
  
 Normalerweise werden die JSON-Serialisierung und-Deserialisierung automatisch von Windows Communication Foundation (WCF) verarbeitet, wenn Sie Daten Vertragstypen in Dienst Vorgängen verwenden, die für AJAX-aktivierte Endpunkte verfügbar gemacht werden. In einigen Fällen müssen Sie jedoch möglicherweise direkt mit JSON-Daten arbeiten.   
  
> [!NOTE]
> Wenn während der Serialisierung einer ausgehenden Antwort auf dem Server oder aus einem anderen Grund ein Fehler auftritt, wird er möglicherweise nicht als Fehler an den Client zurückgegeben.  
  
 Dieser Artikel basiert auf dem Beispiel für eine [JSON-Serialisierung](../samples/json-serialization.md) .  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a>So definieren Sie den Datenvertrag für einen Person-Typ 
  
1. Definieren Sie den Datenvertrag für `Person`, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute> an die Klasse und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut an die zu serialisierenden Member anhängen. Weitere Informationen zu Daten Verträgen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).  
  
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
    var p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2. Serialisieren Sie `Person` das-Objekt mithilfe der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>in einen Speicherdaten Strom.  
  
    ```csharp  
    var stream1 = new MemoryStream();  
    var ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3. Verwenden Sie die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>-Methode, um JSON-Daten in den Stream zu schreiben.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4. Zeigen Sie die JSON-Ausgabe an.  
  
    ```csharp  
    stream1.Position = 0;  
    var sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a>So deserialisieren Sie eine Instanz des Person-Typs von JSON  
  
1. Deserialisieren Sie die JSON-codierten Daten mit der `Person`-Methode des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> in eine neue Instanz von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    stream1.Position = 0;  
    var p2 = (Person)ser.ReadObject(stream1);  
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
    // Create User object.  
    var user = new User("Bob", 42);  
  
    // Create a stream to serialize the object to.  
    var ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    var ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    var deserializedUser = new User();  
    var ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    var ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
> Wie im folgenden Beispiel gezeigt, löst der JSON-Serialisierer eine Serialisierungsausnahme für Datenverträge aus, die mehrere Member mit demselben Namen besitzen:  
  
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
- [Unterstützung für JSON und andere Datenübertragungs Formate](support-for-json-and-other-data-transfer-formats.md)
