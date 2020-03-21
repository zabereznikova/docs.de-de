---
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: 716bcb2bb43656051beffb15da9c7a988942ecd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183794"
---
# <a name="datacontractresolver"></a><span data-ttu-id="a4f71-102">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="a4f71-102">DataContractResolver</span></span>
<span data-ttu-id="a4f71-103">In diesem Beispiel wird veranschaulicht, wie die Serialisierungs- und Deserialisierungsprozesse mit der <xref:System.Runtime.Serialization.DataContractResolver>-Klasse angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="a4f71-103">This sample demonstrates how the serialization and deserialization processes can be customized by using the <xref:System.Runtime.Serialization.DataContractResolver> class.</span></span> <span data-ttu-id="a4f71-104">In diesem Beispiel wird veranschaulicht, wie DataContractResolver verwendet wird, um bei der Serialisierung und der Deserialisierung CLR-Typen einer xsi:type-Darstellung zuzuordnen bzw. diese Zuordnung wieder aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="a4f71-104">This sample shows how to use a DataContractResolver to map CLR types to and from an xsi:type representation during serialization and deserialization.</span></span>

## <a name="sample-details"></a><span data-ttu-id="a4f71-105">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="a4f71-105">Sample Details</span></span>
 <span data-ttu-id="a4f71-106">Im Beispiel werden folgende CLR-Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="a4f71-106">The sample defines the following CLR types.</span></span>

```csharp
using System;
using System.Runtime.Serialization;

namespace Types
{
    [DataContract]
    public class Customer
    {
        [DataMember]
        public string Name { get; set; }
    }

    [DataContract]
    public class VIPCustomer : Customer
    {
        [DataMember]
        public string VipInfo { get; set; }
    }

    [DataContract]
    public class RegularCustomer : Customer
    {
    }

    [DataContract]
    public class PreferredVIPCustomer : VIPCustomer
    {
    }
}
```

 <span data-ttu-id="a4f71-107">Die Assembly wird im Beispiel geladen, wobei jeder dieser Typen extrahiert und dann serialisiert und deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a4f71-107">The sample loads the assembly, extracts each of these types, and then serializes and deserializes them.</span></span> <span data-ttu-id="a4f71-108"><xref:System.Runtime.Serialization.DataContractResolver> wird in den Serialisierungsprozess integriert, indem eine Instanz der von <xref:System.Runtime.Serialization.DataContractResolver> abgeleiteten Klasse an den <xref:System.Runtime.Serialization.DataContractSerializer>-Konstruktor übergeben wird, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4f71-108">The <xref:System.Runtime.Serialization.DataContractResolver> is plugged into the serialization process by passing an instance of the <xref:System.Runtime.Serialization.DataContractResolver>-derived class to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, as shown in the following example.</span></span>

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 <span data-ttu-id="a4f71-109">Anschließend werden die CLR-Typen serialisiert, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4f71-109">The sample then serializes the CLR types as shown in the following code example.</span></span>

```csharp
Assembly assembly = Assembly.Load(new AssemblyName("Types"));

public void serialize(Type type)
{
    Object instance = Activator.CreateInstance(type);

    Console.WriteLine("----------------------------------------");
    Console.WriteLine();
    Console.WriteLine("Serializing type: {0}", type.Name);
    Console.WriteLine();
    this.buffer = new StringBuilder();
    using (XmlWriter xmlWriter = XmlWriter.Create(this.buffer))
    {
        try
        {
            this.serializer.WriteObject(xmlWriter, instance);
        }
        catch (SerializationException error)
        {
            Console.WriteLine(error.ToString());
        }
    }
    Console.WriteLine(this.buffer.ToString());
}
```

 <span data-ttu-id="a4f71-110">Dann werden die xsi:-Typen deserialisiert, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4f71-110">The sample then deserializes the xsi:types as shown in the following code example.</span></span>

```csharp
public void deserialize(Type type)
{
    Console.WriteLine();
    Console.WriteLine("Deserializing type: {0}", type.Name);
    Console.WriteLine();
    using (XmlReader xmlReader = XmlReader.Create(new StringReader(this.buffer.ToString())))
    {
        Object obj = this.serializer.ReadObject(xmlReader);
    }
}
```

 <span data-ttu-id="a4f71-111">Da der benutzerdefinierte <xref:System.Runtime.Serialization.DataContractResolver> an den <xref:System.Runtime.Serialization.DataContractSerializer>-Konstruktor übergeben wird, wird <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> während der Serialisierung aufgerufen, um einen CLR-Typ einem entsprechenden `xsi:type` zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a4f71-111">Since the custom <xref:System.Runtime.Serialization.DataContractResolver> is passed in to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, the <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> is called during serialization to map a CLR type to an equivalent `xsi:type`.</span></span> <span data-ttu-id="a4f71-112">Ebenso wird bei der Deserialisierung <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> aufgerufen, um den `xsi:type` einem entsprechenden CLR-Typ zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a4f71-112">Similarly the <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> is called during deserialization to map the `xsi:type` to an equivalent CLR type.</span></span> <span data-ttu-id="a4f71-113">In diesem Beispiel ist der <xref:System.Runtime.Serialization.DataContractResolver> wie im folgenden Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="a4f71-113">In this sample, the <xref:System.Runtime.Serialization.DataContractResolver> is defined as shown in the following example.</span></span>

 <span data-ttu-id="a4f71-114">Das folgende Codebeispiel ist eine vom <xref:System.Runtime.Serialization.DataContractResolver> abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="a4f71-114">The following code example is a class deriving from <xref:System.Runtime.Serialization.DataContractResolver>.</span></span>

```csharp
class MyDataContractResolver : DataContractResolver
{
    private Dictionary<string, XmlDictionaryString> dictionary = new Dictionary<string, XmlDictionaryString>();
    Assembly assembly;

    public MyDataContractResolver(Assembly assembly)
    {
        this.assembly = assembly;
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        XmlDictionaryString tName;
        XmlDictionaryString tNamespace;
        if (dictionary.TryGetValue(typeName, out tName) && dictionary.TryGetValue(typeNamespace, out tNamespace))
        {
            return this.assembly.GetType(tNamespace.Value + "." + tName.Value);
        }
        else
        {
            return null;
        }
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        string name = dataContractType.Name;
        string namesp = dataContractType.Namespace;
        typeName = new XmlDictionaryString(XmlDictionary.Empty, name, 0);
        typeNamespace = new XmlDictionaryString(XmlDictionary.Empty, namesp, 0);
        if (!dictionary.ContainsKey(dataContractType.Name))
        {
            dictionary.Add(name, typeName);
        }
        if (!dictionary.ContainsKey(dataContractType.Namespace))
        {
            dictionary.Add(namesp, typeNamespace);
        }
    }
}
```

 <span data-ttu-id="a4f71-115">Als Teil des Beispiels generiert das Typenprojekt die Assembly mit allen Typen, die in diesem Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4f71-115">As part of the sample, the Types project generates the assembly with all the types that are used in this sample.</span></span> <span data-ttu-id="a4f71-116">Verwenden Sie dieses Projekt, um die zu serialisierenden Typen hinzuzufügen, zu entfernen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a4f71-116">Use this project to add, remove or modify the types that will be serialized.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="a4f71-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4f71-117">To use this sample</span></span>

1. <span data-ttu-id="a4f71-118">Öffnen Sie mit Visual Studio 2012 die DCRSample.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="a4f71-118">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="a4f71-119">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a4f71-119">To run the solution, press F5</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4f71-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a4f71-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4f71-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a4f71-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a4f71-122">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a4f71-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4f71-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4f71-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a><span data-ttu-id="a4f71-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4f71-124">See also</span></span>

- [<span data-ttu-id="a4f71-125">Verwenden eines Datenvertragsresolvers</span><span class="sxs-lookup"><span data-stu-id="a4f71-125">Using a Data Contract Resolver</span></span>](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)
