---
title: 'Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4fd768a3a254616dc5dd8b5127ec7f794b71159
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="b94df-102">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="b94df-102">How to: Serialize and Deserialize JSON Data</span></span>
<span data-ttu-id="b94df-103">JSON (JavaScript Object Notation) ist ein effizientes Datencodierungsformat, das einen schnellen Austausch kleiner Datenmengen zwischen Clientbrowsern und AJAX-aktivierten Webdiensten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b94df-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="b94df-104">In diesem Thema wird gezeigt, wie .NET-Typobjekte mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> in JSON-codierte Daten serialisiert und Daten im JSON-Format anschließend wieder in Instanzen von .NET-Typen deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b94df-104">This topic demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="b94df-105">Dieses Beispiel verwendet einen Datenvertrag, um die Serialisierung und die Deserialisierung eines benutzerdefinierten `Person`-Typs zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="b94df-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type.</span></span>  
  
 <span data-ttu-id="b94df-106">In der Regel wird die JSON-Serialisierung und -Deserialisierung automatisch von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] vorgenommen, wenn Sie Datenvertragstypen in Dienstvorgängen verwenden, die über AJAX-aktivierte Endpunkte verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b94df-106">Normally, JSON serialization and deserialization is handled automatically by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="b94df-107">In manchen Fällen müssen Sie möglicherweise direkt mit JSON-Daten arbeiten. Dieses Szenario wird in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b94df-107">However, in some cases you may need to work with JSON data directly - this is the scenario that this topic demonstrates.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b94df-108">Wenn bei der Serialisierung einer ausgehenden Antwort auf dem Server ein Fehler auftritt oder wenn der Antwortvorgang aus einem anderen Grund eine Ausnahme auslöst, wird möglicherweise kein Fehler an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b94df-108">If an error occurs during serialization of an outgoing reply on the server or the reply operation throws an exception for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="b94df-109">In diesem Thema beruht auf dem [JSON-Serialisierung](../../../../docs/framework/wcf/samples/json-serialization.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b94df-109">This topic is based on the [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) sample.</span></span>  
  
### <a name="to-define-the-data-contract-for-a-person"></a><span data-ttu-id="b94df-110">So definieren Sie den Datenvertrag für eine Person</span><span class="sxs-lookup"><span data-stu-id="b94df-110">To define the data contract for a Person</span></span>  
  
1.  <span data-ttu-id="b94df-111">Definieren Sie den Datenvertrag für `Person`, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute> an die Klasse und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut an die zu serialisierenden Member anhängen.</span><span class="sxs-lookup"><span data-stu-id="b94df-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b94df-112">Datenverträge, finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="b94df-112"> data contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
    ```  
    [DataContract]  
        internal class Person  
        {  
            [DataMember]  
            internal string name;  
  
            [DataMember]  
            internal int age;  
        }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="b94df-113">So serialisieren Sie eine Instanz des Person-Typs in JSON</span><span class="sxs-lookup"><span data-stu-id="b94df-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="b94df-114">Erstellen Sie eine Instanz des `Person`-Typs.</span><span class="sxs-lookup"><span data-stu-id="b94df-114">Create an instance of the `Person` type.</span></span>  
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="b94df-115">Serialisieren Sie das `Person`-Objekt mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> in einen Speicherstream.</span><span class="sxs-lookup"><span data-stu-id="b94df-115">Serialize the `Person` object to a memory stream using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="b94df-116">Verwenden Sie die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>-Methode, um JSON-Daten in den Stream zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b94df-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="b94df-117">Zeigen Sie die JSON-Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="b94df-117">Show the JSON output.</span></span>  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="b94df-118">So deserialisieren Sie eine Instanz des Person-Typs von JSON</span><span class="sxs-lookup"><span data-stu-id="b94df-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="b94df-119">Deserialisieren Sie die JSON-codierten Daten mit der `Person`-Methode des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> in eine neue Instanz von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b94df-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="b94df-120">Zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="b94df-120">Show the results.</span></span>  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a><span data-ttu-id="b94df-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b94df-121">Example</span></span>  
  
```  
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
>  <span data-ttu-id="b94df-122">Wie im folgenden Beispiel gezeigt, löst der JSON-Serialisierer eine Serialisierungsausnahme für Datenverträge aus, die mehrere Member mit demselben Namen besitzen:</span><span class="sxs-lookup"><span data-stu-id="b94df-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="b94df-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b94df-123">See Also</span></span>  
 [<span data-ttu-id="b94df-124">Eigenständige JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b94df-124">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="b94df-125">Unterstützung für JSON und andere Datenübertragungsformate</span><span class="sxs-lookup"><span data-stu-id="b94df-125">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
