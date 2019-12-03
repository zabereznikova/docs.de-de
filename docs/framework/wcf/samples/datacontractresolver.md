---
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: 101c33ca197be9dff52a73c844dd0b006e62b2ac
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716592"
---
# <a name="datacontractresolver"></a>DataContractResolver
In diesem Beispiel wird veranschaulicht, wie die Serialisierungs- und Deserialisierungsprozesse mit der <xref:System.Runtime.Serialization.DataContractResolver>-Klasse angepasst werden können. In diesem Beispiel wird veranschaulicht, wie DataContractResolver verwendet wird, um bei der Serialisierung und der Deserialisierung CLR-Typen einer xsi:type-Darstellung zuzuordnen bzw. diese Zuordnung wieder aufzuheben.

## <a name="sample-details"></a>Beispieldetails
 Im Beispiel werden folgende CLR-Typen definiert.

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

 Die Assembly wird im Beispiel geladen, wobei jeder dieser Typen extrahiert und dann serialisiert und deserialisiert wird. <xref:System.Runtime.Serialization.DataContractResolver> wird in den Serialisierungsprozess integriert, indem eine Instanz der von <xref:System.Runtime.Serialization.DataContractResolver> abgeleiteten Klasse an den <xref:System.Runtime.Serialization.DataContractSerializer>-Konstruktor übergeben wird, wie im folgenden Beispiel gezeigt.

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 Anschließend werden die CLR-Typen serialisiert, wie im folgenden Codebeispiel gezeigt.

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

 Dann werden die xsi:-Typen deserialisiert, wie im folgenden Codebeispiel gezeigt.

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

 Da der benutzerdefinierte <xref:System.Runtime.Serialization.DataContractResolver> an den <xref:System.Runtime.Serialization.DataContractSerializer>-Konstruktor übergeben wird, wird <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> während der Serialisierung aufgerufen, um einen CLR-Typ einem entsprechenden `xsi:type` zuzuordnen. Ebenso wird bei der Deserialisierung <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> aufgerufen, um den `xsi:type` einem entsprechenden CLR-Typ zuzuordnen. In diesem Beispiel ist der <xref:System.Runtime.Serialization.DataContractResolver> wie im folgenden Beispiel definiert.

 Das folgende Codebeispiel ist eine vom <xref:System.Runtime.Serialization.DataContractResolver> abgeleitete Klasse.

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

 Als Teil des Beispiels generiert das Typenprojekt die Assembly mit allen Typen, die in diesem Beispiel verwendet werden. Verwenden Sie dieses Projekt, um die zu serialisierenden Typen hinzuzufügen, zu entfernen oder zu ändern.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2012 die Projektmappendatei "DCRSample. sln".

2. Drücken Sie F5, um die Projektmappe auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Datenvertragsresolvers](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)
