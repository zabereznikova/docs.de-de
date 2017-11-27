---
title: Interoperable Objektverweise
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6d55ffb6ed08b4642bc72c1eabb60164b6c744c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
