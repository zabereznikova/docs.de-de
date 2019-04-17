---
title: Interoperable Objektverweise
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610638"
---
# <a name="interoperable-object-references"></a>Interoperable Objektverweise
In der Standardeinstellung <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert Objekte nach Wert. Sie können die <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> Eigenschaft anweisen, Objektverweise beizubehalten, beim Serialisieren von Objekten der Datenvertrags-Serialisierer.  
  
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
  
 Allerdings <xref:System.Runtime.Serialization.XsdDataContractExporter> beschreibt nicht die `id` und `ref` Attribute im Schema, auch dann, wenn die `preserveObjectReferences` -Eigenschaftensatz auf `true`.  
  
## <a name="using-isreference"></a>Verwenden von IsReference  
 Zum Generieren von objektverweisinformationen, die gemäß dem Schema gültig ist, die es wird beschrieben, gelten die <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf einen Typ aus, und legen die <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag `true`. Das folgende Beispiel ändert die Klasse `X` im vorherigen Beispiel durch Hinzufügen von `IsReference`:  
  
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
  
 Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet. Ohne diese, wenn ein Typ, aus dem Schema generiert wird, Ausgabe der XML-Code, dass der Typ nicht unbedingt mit dem ursprünglich angenommenen Schema kompatibel ist. Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen. Mit `IsReference` auf einen Datenmember angewendet, das Element als erkannt werden weiterhin *referenzierbare* beim Roundtrip ausgeführt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
