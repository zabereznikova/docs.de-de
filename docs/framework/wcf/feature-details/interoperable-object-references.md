---
title: Interoperable Objektverweise
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 0927f217a1666f8f27ca9c3e68f80a96b9c0f2b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184703"
---
# <a name="interoperable-object-references"></a>Interoperable Objektverweise
Standardmäßig <xref:System.Runtime.Serialization.DataContractSerializer> werden Objekte nach Wert serialisiert. Sie können <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> die Eigenschaft verwenden, um den Datenvertragsserialisierungser anzuweisen, Objektverweise beim Serialisieren von Objekten beizubehalten.  
  
## <a name="generated-xml"></a>Generierte XML  
 Betrachten Sie als Beispiel das folgende Objekt:  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `false` festgelegt (Standardeinstellung), wird die folgende XML generiert:  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `true` festgelegt, wird die folgende XML generiert:  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <xref:System.Runtime.Serialization.XsdDataContractExporter> Beschreibt jedoch nicht die `id` `ref` und-Attribute in seinem Schema, auch wenn die `preserveObjectReferences` Eigenschaft auf `true`festgelegt ist.  
  
## <a name="using-isreference"></a>Verwenden von IsReference  
 Um Objektreferenzinformationen zu generieren, die gemäß dem Schema <xref:System.Runtime.Serialization.DataContractAttribute> gültig sind, das sie <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> beschreibt, wenden Sie das Attribut auf einen Typ an, und legen Sie das Flag auf fest. `true` Im folgenden Beispiel wird `X` die Klasse im `IsReference`vorherigen Beispiel geändert, indem Folgendes hinzugefügt wird:  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 Folgende XML wird generiert:  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet. Wenn ein Typ aus dem Schema generiert wird, ist die XML-Ausgabe für diesen Typ nicht unbedingt mit dem ursprünglich angenommenen Schema kompatibel. Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen. Bei `IsReference` Anwendung auf ein Datenelement wird das Element weiterhin als *referenzierbar* erkannt, wenn es gerundt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
