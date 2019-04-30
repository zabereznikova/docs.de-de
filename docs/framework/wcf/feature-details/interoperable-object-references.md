---
title: Interoperable Objektverweise
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918969"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="65ddc-102">Interoperable Objektverweise</span><span class="sxs-lookup"><span data-stu-id="65ddc-102">Interoperable object references</span></span>
<span data-ttu-id="65ddc-103">In der Standardeinstellung <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert Objekte nach Wert.</span><span class="sxs-lookup"><span data-stu-id="65ddc-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="65ddc-104">Sie können die <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> Eigenschaft anweisen, Objektverweise beizubehalten, beim Serialisieren von Objekten der Datenvertrags-Serialisierer.</span><span class="sxs-lookup"><span data-stu-id="65ddc-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="65ddc-105">Generierte XML</span><span class="sxs-lookup"><span data-stu-id="65ddc-105">Generated XML</span></span>  
 <span data-ttu-id="65ddc-106">Betrachten Sie als Beispiel das folgende Objekt:</span><span class="sxs-lookup"><span data-stu-id="65ddc-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="65ddc-107">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `false` festgelegt (Standardeinstellung), wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="65ddc-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="65ddc-108">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `true` festgelegt, wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="65ddc-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="65ddc-109">Allerdings <xref:System.Runtime.Serialization.XsdDataContractExporter> beschreibt nicht die `id` und `ref` Attribute im Schema, auch dann, wenn die `preserveObjectReferences` -Eigenschaftensatz auf `true`.</span><span class="sxs-lookup"><span data-stu-id="65ddc-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="65ddc-110">Verwenden von IsReference</span><span class="sxs-lookup"><span data-stu-id="65ddc-110">Using IsReference</span></span>  
 <span data-ttu-id="65ddc-111">Zum Generieren von objektverweisinformationen, die gemäß dem Schema gültig ist, die es wird beschrieben, gelten die <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf einen Typ aus, und legen die <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag `true`.</span><span class="sxs-lookup"><span data-stu-id="65ddc-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="65ddc-112">Das folgende Beispiel ändert die Klasse `X` im vorherigen Beispiel durch Hinzufügen von `IsReference`:</span><span class="sxs-lookup"><span data-stu-id="65ddc-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="65ddc-113">Folgende XML wird generiert:</span><span class="sxs-lookup"><span data-stu-id="65ddc-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A> 
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="65ddc-114">Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="65ddc-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="65ddc-115">Ohne diese, wenn ein Typ, aus dem Schema generiert wird, Ausgabe der XML-Code, dass der Typ nicht unbedingt mit dem ursprünglich angenommenen Schema kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="65ddc-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="65ddc-116">Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen.</span><span class="sxs-lookup"><span data-stu-id="65ddc-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="65ddc-117">Mit `IsReference` auf einen Datenmember angewendet, das Element als erkannt werden weiterhin *referenzierbare* beim Roundtrip ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="65ddc-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ddc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65ddc-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
