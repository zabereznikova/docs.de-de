---
title: Interoperable Objekt Verweise
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: bf395c187c46e88406bfb81798c7e359b48255e3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263229"
---
# <a name="interoperable-object-references"></a>Interoperable Objekt Verweise

Standardmäßig <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert Objekte nach Wert. Sie können die- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> Eigenschaft verwenden, um den Datenvertragsserialisierer anzuweisen, beim Serialisieren von Objekten Objekt Verweise beizubehalten.  
  
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
  
 Beschreibt jedoch <xref:System.Runtime.Serialization.XsdDataContractExporter> nicht das `id` -Attribut und das- `ref` Attribut im Schema, auch wenn die- `preserveObjectReferences` Eigenschaft auf festgelegt ist `true` .  
  
## <a name="using-isreference"></a>Verwenden von IsReference  

 Um Objekt Verweis Informationen zu generieren, die gemäß dem Schema, das Sie beschreibt, gültig ist, wenden Sie das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf einen Typ an, und legen Sie das- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> Flag auf fest `true` . Im folgenden Beispiel wird die-Klasse `X` im vorherigen Beispiel geändert, indem Folgendes hinzugefügt wird `IsReference` :  
  
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
  
 Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet. Wenn ein Typ aus dem Schema generiert wird, ist die XML-Ausgabe für diesen Typ nicht notwendigerweise kompatibel mit dem ursprünglich angenommenen Schema. Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen. `IsReference`Wenn Sie auf einen Datenmember angewendet wird, wird der Member weiterhin als *referenzierbar* erkannt, wenn ein Roundtrip ausgeführt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
