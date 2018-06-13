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
# <a name="interoperable-object-references"></a><span data-ttu-id="36daf-102">Interoperable Objektverweise</span><span class="sxs-lookup"><span data-stu-id="36daf-102">Interoperable Object References</span></span>
<span data-ttu-id="36daf-103">Standardmäßig serialisiert der <xref:System.Runtime.Serialization.DataContractSerializer> Objekte anhand des Werts.</span><span class="sxs-lookup"><span data-stu-id="36daf-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="36daf-104">Mithilfe der <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>-Eigenschaft können Sie den Datenvertragsserialisierer anweisen, die Objektverweise beim Serialisieren von Objekten des Typs beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="36daf-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="36daf-105">Generierte XML</span><span class="sxs-lookup"><span data-stu-id="36daf-105">Generated XML</span></span>  
 <span data-ttu-id="36daf-106">Betrachten Sie als Beispiel das folgende Objekt:</span><span class="sxs-lookup"><span data-stu-id="36daf-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="36daf-107">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `false` festgelegt (Standardeinstellung), wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="36daf-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="36daf-108">Ist <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> auf `true` festgelegt, wird die folgende XML generiert:</span><span class="sxs-lookup"><span data-stu-id="36daf-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="36daf-109"><xref:System.Runtime.Serialization.XsdDataContractExporter> beschreibt jedoch nicht das `id`- und das `ref`-Attribut im Schema. Dies ist auch dann der Fall, wenn die `preserveObjectReferences`-Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="36daf-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="36daf-110">Verwenden von IsReference</span><span class="sxs-lookup"><span data-stu-id="36daf-110">Using IsReference</span></span>  
 <span data-ttu-id="36daf-111">Wenden Sie zum Generieren von Objektverweisinformationen, die gemäß dem beschreibenden Schema gültig sind, das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf einen Typ an, und legen Sie das <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>-Flag auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="36daf-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="36daf-112">Verwendung von `IsReference` in der vorherigen `X`-Beispielklasse:</span><span class="sxs-lookup"><span data-stu-id="36daf-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
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
  
 <span data-ttu-id="36daf-113">Folgende XML wird generiert:</span><span class="sxs-lookup"><span data-stu-id="36daf-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="36daf-114">Durch die Verwendung von `IsReference` wird die Kompatibilität für Nachrichten-Roundtrips gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="36daf-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="36daf-115">Wird dieses Element nicht verwendet, wird beim Erstellen eines Typs aus dem Schema nicht unbedingt eine XML für diesen Typ zurückgesendet, die mit dem ursprünglich angenommenen Schema kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="36daf-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="36daf-116">Mit anderen Worten: Obgleich das `id`- und das `ref`-Attribut serialisiert wurden, wurde durch das ursprüngliche Schema möglicherweise verhindert, dass diese Attribute (oder alle Attribute) in der XML erscheinen.</span><span class="sxs-lookup"><span data-stu-id="36daf-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="36daf-117">Wurde `IsReference` auf einen Datenmember angewendet, gilt der Member bei Roundtrips auch weiterhin als "verweisbar".</span><span class="sxs-lookup"><span data-stu-id="36daf-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36daf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36daf-118">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
