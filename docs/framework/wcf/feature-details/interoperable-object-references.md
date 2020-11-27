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
# <a name="interoperable-object-references"></a><span data-ttu-id="15064-102">Interoperable Objekt Verweise</span><span class="sxs-lookup"><span data-stu-id="15064-102">Interoperable object references</span></span>

<span data-ttu-id="15064-103">Standardmäßig <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert Objekte nach Wert.</span><span class="sxs-lookup"><span data-stu-id="15064-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="15064-104">Sie können die- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> Eigenschaft verwenden, um den Datenvertragsserialisierer anzuweisen, beim Serialisieren von Objekten Objekt Verweise beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="15064-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="15064-105">Generierte XML</span><span class="sxs-lookup"><span data-stu-id="15064-105">Generated XML</span></span>  

 <span data-ttu-id="15064-106">Betrachten Sie als Beispiel das folgende Objekt:</span><span class="sxs-lookup"><span data-stu-id="15064-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="15064-107">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `false` festgelegt (Standardeinstellung), wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="15064-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="15064-108">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `true` festgelegt, wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="15064-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="15064-109">Beschreibt jedoch <xref:System.Runtime.Serialization.XsdDataContractExporter> nicht das `id` -Attribut und das- `ref` Attribut im Schema, auch wenn die- `preserveObjectReferences` Eigenschaft auf festgelegt ist `true` .</span><span class="sxs-lookup"><span data-stu-id="15064-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="15064-110">Verwenden von IsReference</span><span class="sxs-lookup"><span data-stu-id="15064-110">Using IsReference</span></span>  

 <span data-ttu-id="15064-111">Um Objekt Verweis Informationen zu generieren, die gemäß dem Schema, das Sie beschreibt, gültig ist, wenden Sie das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf einen Typ an, und legen Sie das- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> Flag auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="15064-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="15064-112">Im folgenden Beispiel wird die-Klasse `X` im vorherigen Beispiel geändert, indem Folgendes hinzugefügt wird `IsReference` :</span><span class="sxs-lookup"><span data-stu-id="15064-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="15064-113">Folgende XML wird generiert:</span><span class="sxs-lookup"><span data-stu-id="15064-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="15064-114">Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="15064-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="15064-115">Wenn ein Typ aus dem Schema generiert wird, ist die XML-Ausgabe für diesen Typ nicht notwendigerweise kompatibel mit dem ursprünglich angenommenen Schema.</span><span class="sxs-lookup"><span data-stu-id="15064-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="15064-116">Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen.</span><span class="sxs-lookup"><span data-stu-id="15064-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="15064-117">`IsReference`Wenn Sie auf einen Datenmember angewendet wird, wird der Member weiterhin als *referenzierbar* erkannt, wenn ein Roundtrip ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15064-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15064-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15064-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
