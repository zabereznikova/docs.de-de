---
title: Verwenden eines Datenvertragsresolvers
ms.date: 03/30/2017
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
ms.openlocfilehash: 20abd4d928fc51eb359949ecbb216615e9659b7f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595023"
---
# <a name="using-a-data-contract-resolver"></a>Verwenden eines Datenvertragsresolvers
Mithilfe eines Datenvertragsresolver können Sie bekannte Typen dynamisch konfigurieren. Bekannte Typen sind erforderlich, wenn ein Typ serialisiert oder deserialisiert wird, der von einem Datenvertrag nicht erwartet wird. Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](data-contract-known-types.md). Bekannte Typen werden in der Regel statisch angegeben. Das bedeutet, dass Sie beim Implementieren eines Vorgangs alle möglichen Typen kennen müssen, die der Vorgang erhalten kann. In einigen Szenarios trifft dies nicht zu, und es ist wichtig, bekannte Typen dynamisch angeben zu können.  
  
## <a name="creating-a-data-contract-resolver"></a>Erstellen eines Datenvertragsresolvers  
 Das Erstellen eines Datenvertragsresolvers umfasst die Implementierung von zwei Methoden: <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> und <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>. Diese beiden Methoden implementieren Rückrufe, die jeweils während der Serialisierung und der Deserialisierung verwendet werden. Die <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A>-Methode wird während der Serialisierung aufgerufen. Sie verwendet einen Datenvertragstyp und ordnet diesen einem `xsi:type`-Namen und einem Namespace zu. Die <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>-Methode wird während der Deserialisierung aufgerufen. Sie verwendet einen `xsi:type`-Namen und einen Namespace und löst diesen zu einem Datenvertragstyp auf. Beide Methoden verfügen über einen `knownTypeResolver`-Parameter, der verwendet werden kann, um den standardmäßigen bekannten Typresolver in der Implementierung zu verwenden.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie einen <xref:System.Runtime.Serialization.DataContractResolver> implementieren, um die Zuordnung zu und von einem Datenvertragstyp mit dem Namen `Customer` vorzunehmen, der vom einem Datenvertragstyp `Person` abgeleitet wurde.  
  
```csharp  
public class MyCustomerResolver : DataContractResolver  
{  
    public override bool TryResolveType(Type dataContractType, Type declaredType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        if (dataContractType == typeof(Customer))  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add("SomeCustomer");  
            typeNamespace = dictionary.Add("http://tempuri.com");  
            return true;  
        }  
        else  
        {  
            return knownTypeResolver.TryResolveType(dataContractType, declaredType, null, out typeName, out typeNamespace);  
        }  
    }  
  
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        if (typeName == "SomeCustomer" && typeNamespace == "http://tempuri.com")  
        {  
            return typeof(Customer);  
        }  
        else  
        {  
            return knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        }  
    }  
}  
```  
  
 Nachdem Sie einen <xref:System.Runtime.Serialization.DataContractResolver> definiert haben, können Sie diesen verwenden, indem Sie ihn an den <xref:System.Runtime.Serialization.DataContractSerializer>-Konstruktor übergeben. Dies ist im folgenden Beispiel dargestellt.  
  
```csharp
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 Sie können einen <xref:System.Runtime.Serialization.DataContractResolver> in einem Aufruf der Methoden <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> oder <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType> angeben, wie im folgenden Beispiel gezeigt.  
  
```csharp
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 Sie können ihn jedoch auch unter <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> festlegen, wie im folgenden Beispiel gezeigt.  
  
```csharp
ServiceHost host = new ServiceHost(typeof(MyService));  
  
ContractDescription cd = host.Description.Endpoints[0].Contract;  
OperationDescription myOperationDescription = cd.Operations.Find("Echo");  
  
DataContractSerializerOperationBehavior serializerBehavior = myOperationDescription.Behaviors.Find<DataContractSerializerOperationBehavior>();  
if (serializerBehavior == null)  
{  
    serializerBehavior = new DataContractSerializerOperationBehavior(myOperationDescription);  
    myOperationDescription.Behaviors.Add(serializerBehavior);  
}  
  
SerializerBehavior.DataContractResolver = new MyCustomerResolver();  
```  
  
 Sie können einen Datenvertragsresolver deklarativ angeben, indem Sie ein Attribut implementieren, das auf einen Dienst angewendet werden kann.  Weitere Informationen finden Sie im Beispiel für das [knownassemblyattribute](../samples/knownassemblyattribute.md) -Beispiel. In diesem Beispiel wird ein Attribut mit dem Namen "KnownAssembly" implementiert, mit dem dem Dienst Verhalten ein benutzerdefinierter datenvertragsresolver hinzugefügt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Bekannte Typen in Datenverträgen](data-contract-known-types.md)
- [DataContractSerializer-Beispiel](../samples/datacontractserializer-sample.md)
- [KnownAssemblyAttribute](../samples/knownassemblyattribute.md)
