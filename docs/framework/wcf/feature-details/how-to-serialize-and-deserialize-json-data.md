---
title: 'Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 6363a8e161969c188c5dd18c425ffd42969e9adc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106157"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="83092-102">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="83092-102">How to: Serialize and deserialize JSON data</span></span>
<span data-ttu-id="83092-103">JSON (JavaScript Object Notation) ist ein effizientes Datencodierungsformat, das einen schnellen Austausch kleiner Datenmengen zwischen Clientbrowsern und AJAX-aktivierten Webdiensten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="83092-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="83092-104">In diesem Artikel wird veranschaulicht, wie .NET Type-Objekten in JSON-codierte Daten serialisiert und Daten im JSON-Format anschließend wieder in Instanzen von .NET-Typen deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="83092-104">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="83092-105">Dieses Beispiel verwendet einen Datenvertrag, um Serialisierung und Deserialisierung von einer benutzerdefinierten veranschaulichen `Person` Typ und verwendet <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="83092-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
 <span data-ttu-id="83092-106">Normalerweise werden JSON-Serialisierung und Deserialisierung automatisch von Windows Communication Foundation (WCF) behandelt, wenn Sie Datenvertragstypen in Dienstvorgängen verwenden, die über AJAX-aktivierte Endpunkte verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="83092-106">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="83092-107">In einigen Fällen müssen Sie jedoch direkt mit JSON-Daten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="83092-107">However, in some cases you may need to work with JSON data directly.</span></span>   
  
> [!NOTE]
>  <span data-ttu-id="83092-108">Wenn ein Fehler während der Serialisierung einer ausgehenden Antwort auf dem Server oder einem anderen Grund auftritt, wird möglicherweise nicht an den Client als Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="83092-108">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="83092-109">Dieser Artikel basiert auf der [JSON-Serialisierung](../samples/json-serialization.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="83092-109">This article is based on the [JSON serialization](../samples/json-serialization.md) sample.</span></span>  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="83092-110">Definiert den Datenvertrag für einen Typ "Person"</span><span class="sxs-lookup"><span data-stu-id="83092-110">To define the data contract for a Person type</span></span> 
  
1.  <span data-ttu-id="83092-111">Definieren Sie den Datenvertrag für `Person`, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute> an die Klasse und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut an die zu serialisierenden Member anhängen.</span><span class="sxs-lookup"><span data-stu-id="83092-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="83092-112">Weitere Informationen zu Datenverträgen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="83092-112">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>  
  
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
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="83092-113">So serialisieren Sie eine Instanz des Person-Typs in JSON</span><span class="sxs-lookup"><span data-stu-id="83092-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="83092-114">Erstellen Sie eine Instanz des `Person`-Typs.</span><span class="sxs-lookup"><span data-stu-id="83092-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="83092-115">Serialisieren der `Person` Objekt in einen Speicherdatenstrom mit den <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="83092-115">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="83092-116">Verwenden Sie die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>-Methode, um JSON-Daten in den Stream zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="83092-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="83092-117">Zeigen Sie die JSON-Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="83092-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="83092-118">So deserialisieren Sie eine Instanz des Person-Typs von JSON</span><span class="sxs-lookup"><span data-stu-id="83092-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="83092-119">Deserialisieren Sie die JSON-codierten Daten mit der `Person`-Methode des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> in eine neue Instanz von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="83092-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="83092-120">Zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="83092-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="83092-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83092-121">Example</span></span>  
  
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
>  <span data-ttu-id="83092-122">Wie im folgenden Beispiel gezeigt, löst der JSON-Serialisierer eine Serialisierungsausnahme für Datenverträge aus, die mehrere Member mit demselben Namen besitzen:</span><span class="sxs-lookup"><span data-stu-id="83092-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83092-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83092-123">See also</span></span>

- [<span data-ttu-id="83092-124">Eigenständige JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="83092-124">Stand-alone JSON serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="83092-125">Unterstützung für JSON und andere datenübertragungs-Formate</span><span class="sxs-lookup"><span data-stu-id="83092-125">Support for JSON and other data transfer formats</span></span>](support-for-json-and-other-data-transfer-formats.md)
