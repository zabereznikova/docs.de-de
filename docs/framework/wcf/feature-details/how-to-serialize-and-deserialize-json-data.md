---
title: 'Gewusst wie: Verwenden von DataContractJsonSerializer'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 3cf8cc52587a64e7273ab9e0de0b1751d00827cf
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901215"
---
# <a name="how-to-use-datacontractjsonserializer"></a><span data-ttu-id="8d502-102">Verwenden von DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="8d502-102">How to use DataContractJsonSerializer</span></span>

> [!NOTE]
> <span data-ttu-id="8d502-103">In diesem Artikel geht es um <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8d502-103">This article is about <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="8d502-104">In den meisten Szenarien, in denen JSON serialisiert und deserialisiert wird, empfehlen wir die APIs im [System. Text. Json-Namespace](../../../standard/serialization/system-text-json-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8d502-104">For most scenarios that involve serializing and deserializing JSON, we recommend the APIs in the [System.Text.Json namespace](../../../standard/serialization/system-text-json-overview.md).</span></span>

<span data-ttu-id="8d502-105">JSON (JavaScript Object Notation) ist ein effizientes Datencodierungsformat, das einen schnellen Austausch kleiner Datenmengen zwischen Clientbrowsern und AJAX-aktivierten Webdiensten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8d502-105">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>

<span data-ttu-id="8d502-106">In diesem Artikel wird veranschaulicht, wie .net-Typobjekte in JSON-codierte Daten serialisiert und anschließend Daten im JSON-Format wieder in Instanzen von .NET-Typen deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d502-106">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="8d502-107">In diesem Beispiel wird ein Datenvertrag verwendet, um die Serialisierung und Deserialisierung eines benutzerdefinierten `Person` Typs zu veranschaulichen und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d502-107">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<span data-ttu-id="8d502-108">Normalerweise werden die JSON-Serialisierung und-Deserialisierung automatisch von Windows Communication Foundation (WCF) verarbeitet, wenn Sie Daten Vertragstypen in Dienst Vorgängen verwenden, die für AJAX-aktivierte Endpunkte verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="8d502-108">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="8d502-109">In einigen Fällen müssen Sie jedoch möglicherweise direkt mit JSON-Daten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8d502-109">However, in some cases you may need to work with JSON data directly.</span></span>

<span data-ttu-id="8d502-110">Dieser Artikel basiert auf dem [Beispiel DataContractJsonSerializer](../samples/json-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="8d502-110">This article is based on the [DataContractJsonSerializer sample](../samples/json-serialization.md).</span></span>

## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="8d502-111">So definieren Sie den Datenvertrag für einen Person-Typ</span><span class="sxs-lookup"><span data-stu-id="8d502-111">To define the data contract for a Person type</span></span>

1. <span data-ttu-id="8d502-112">Definieren Sie den Datenvertrag für `Person`, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute> an die Klasse und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut an die zu serialisierenden Member anhängen.</span><span class="sxs-lookup"><span data-stu-id="8d502-112">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="8d502-113">Weitere Informationen zu Daten Verträgen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="8d502-113">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>

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

## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="8d502-114">So serialisieren Sie eine Instanz des Person-Typs in JSON</span><span class="sxs-lookup"><span data-stu-id="8d502-114">To serialize an instance of type Person to JSON</span></span>

> [!NOTE]
> <span data-ttu-id="8d502-115">Wenn während der Serialisierung einer ausgehenden Antwort auf dem Server oder aus einem anderen Grund ein Fehler auftritt, wird er möglicherweise nicht als Fehler an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8d502-115">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>

1. <span data-ttu-id="8d502-116">Erstellen Sie eine Instanz des `Person`-Typs.</span><span class="sxs-lookup"><span data-stu-id="8d502-116">Create an instance of the `Person` type.</span></span>

    ```csharp
    var p = new Person();
    p.name = "John";
    p.age = 42;
    ```

2. <span data-ttu-id="8d502-117">Serialisieren Sie das `Person`-Objekt mithilfe des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>in einen Speicherdaten Strom.</span><span class="sxs-lookup"><span data-stu-id="8d502-117">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

    ```csharp
    var stream1 = new MemoryStream();
    var ser = new DataContractJsonSerializer(typeof(Person));
    ```

3. <span data-ttu-id="8d502-118">Verwenden Sie die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>-Methode, um JSON-Daten in den Stream zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8d502-118">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>

    ```csharp
    ser.WriteObject(stream1, p);
    ```

4. <span data-ttu-id="8d502-119">Zeigen Sie die JSON-Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="8d502-119">Show the JSON output.</span></span>

    ```csharp
    stream1.Position = 0;
    var sr = new StreamReader(stream1);
    Console.Write("JSON form of Person object: ");
    Console.WriteLine(sr.ReadToEnd());
    ```

## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="8d502-120">So deserialisieren Sie eine Instanz des Person-Typs von JSON</span><span class="sxs-lookup"><span data-stu-id="8d502-120">To deserialize an instance of type Person from JSON</span></span>

1. <span data-ttu-id="8d502-121">Deserialisieren Sie die JSON-codierten Daten mit der `Person`-Methode des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> in eine neue Instanz von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8d502-121">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

    ```csharp
    stream1.Position = 0;
    var p2 = (Person)ser.ReadObject(stream1);
    ```

2. <span data-ttu-id="8d502-122">Zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="8d502-122">Show the results.</span></span>

    ```csharp
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");
    ```

## <a name="example"></a><span data-ttu-id="8d502-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d502-123">Example</span></span>

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
> <span data-ttu-id="8d502-124">Wie im folgenden Beispiel gezeigt, löst der JSON-Serialisierer eine Serialisierungsausnahme für Datenverträge aus, die mehrere Member mit demselben Namen besitzen:</span><span class="sxs-lookup"><span data-stu-id="8d502-124">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8d502-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d502-125">See also</span></span>

- [<span data-ttu-id="8d502-126">JSON-Serialisierung in .net</span><span class="sxs-lookup"><span data-stu-id="8d502-126">JSON serialization in .NET</span></span>](../../../standard/serialization/system-text-json-overview.md)
