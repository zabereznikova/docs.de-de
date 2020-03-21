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
# <a name="interoperable-object-references"></a><span data-ttu-id="ebeb7-102">Interoperable Objektverweise</span><span class="sxs-lookup"><span data-stu-id="ebeb7-102">Interoperable object references</span></span>
<span data-ttu-id="ebeb7-103">Standardmäßig <xref:System.Runtime.Serialization.DataContractSerializer> werden Objekte nach Wert serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ebeb7-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="ebeb7-104">Sie können <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> die Eigenschaft verwenden, um den Datenvertragsserialisierungser anzuweisen, Objektverweise beim Serialisieren von Objekten beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="ebeb7-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="ebeb7-105">Generierte XML</span><span class="sxs-lookup"><span data-stu-id="ebeb7-105">Generated XML</span></span>  
 <span data-ttu-id="ebeb7-106">Betrachten Sie als Beispiel das folgende Objekt:</span><span class="sxs-lookup"><span data-stu-id="ebeb7-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="ebeb7-107">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `false` festgelegt (Standardeinstellung), wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="ebeb7-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="ebeb7-108">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `true` festgelegt, wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="ebeb7-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="ebeb7-109"><xref:System.Runtime.Serialization.XsdDataContractExporter> Beschreibt jedoch nicht die `id` `ref` und-Attribute in seinem Schema, auch wenn die `preserveObjectReferences` Eigenschaft auf `true`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ebeb7-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="ebeb7-110">Verwenden von IsReference</span><span class="sxs-lookup"><span data-stu-id="ebeb7-110">Using IsReference</span></span>  
 <span data-ttu-id="ebeb7-111">Um Objektreferenzinformationen zu generieren, die gemäß dem Schema <xref:System.Runtime.Serialization.DataContractAttribute> gültig sind, das sie <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> beschreibt, wenden Sie das Attribut auf einen Typ an, und legen Sie das Flag auf fest. `true`</span><span class="sxs-lookup"><span data-stu-id="ebeb7-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="ebeb7-112">Im folgenden Beispiel wird `X` die Klasse im `IsReference`vorherigen Beispiel geändert, indem Folgendes hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="ebeb7-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="ebeb7-113">Folgende XML wird generiert:</span><span class="sxs-lookup"><span data-stu-id="ebeb7-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="ebeb7-114">Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="ebeb7-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="ebeb7-115">Wenn ein Typ aus dem Schema generiert wird, ist die XML-Ausgabe für diesen Typ nicht unbedingt mit dem ursprünglich angenommenen Schema kompatibel.</span><span class="sxs-lookup"><span data-stu-id="ebeb7-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="ebeb7-116">Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen.</span><span class="sxs-lookup"><span data-stu-id="ebeb7-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="ebeb7-117">Bei `IsReference` Anwendung auf ein Datenelement wird das Element weiterhin als *referenzierbar* erkannt, wenn es gerundt wird.</span><span class="sxs-lookup"><span data-stu-id="ebeb7-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebeb7-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebeb7-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
