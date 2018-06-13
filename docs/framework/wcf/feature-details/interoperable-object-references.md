---
title: Interoperable Objektverweise
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: eeedd39ec14a6758395aee1f4c3b8ab26a0c2ffd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493572"
---
# <a name="interoperable-object-references"></a>Interoperable Objektverweise
Standardmäßig serialisiert der <xref:System.Runtime.Serialization.DataContractSerializer> Objekte anhand des Werts. Mithilfe der <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>-Eigenschaft können Sie den Datenvertragsserialisierer anweisen, die Objektverweise beim Serialisieren von Objekten des Typs beizubehalten.  
  
## <a name="generated-xml"></a>Generierte XML  
 Betrachten Sie als Beispiel das folgende Objekt:  
  
```  
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
   <B ref="1" />  
</X>  
```  
  
 <xref:System.Runtime.Serialization.XsdDataContractExporter> beschreibt jedoch nicht das `id`- und das `ref`-Attribut im Schema. Dies ist auch dann der Fall, wenn die `preserveObjectReferences`-Eigenschaft auf `true` festgelegt ist.  
  
## <a name="using-isreference"></a>Verwenden von IsReference  
 Wenden Sie zum Generieren von Objektverweisinformationen, die gemäß dem beschreibenden Schema gültig sind, das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf einen Typ an, und legen Sie das <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>-Flag auf `true` fest. Verwendung von `IsReference` in der vorherigen `X`-Beispielklasse:  
  
 `[DataContract(IsReference=true)] public class X`  
  
 `{`  
  
 `SomeClass someInstance = new SomeClass();`  
  
 `[DataMember]`  
  
 `public SomeClass A = someInstance;`  
  
 `[DataMember]`  
  
 `public SomeClass B = someInstance;`  
  
 `}`  
  
 `public class SomeClass`  
  
 `{`  
  
 `}`  
  
 Folgende XML wird generiert:  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet. Wird dieses Element nicht verwendet, wird beim Erstellen eines Typs aus dem Schema nicht unbedingt eine XML für diesen Typ zurückgesendet, die mit dem ursprünglich angenommenen Schema kompatibel ist. Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen. Wurde `IsReference` auf einen Datenmember angewendet, gilt der Member bei Roundtrips auch weiterhin als "verweisbar".  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
