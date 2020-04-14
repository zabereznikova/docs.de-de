---
title: Serialisierung und Metadaten
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: 7c6fe241fbf92f52abfa0eb66c37bff4d227b4e5
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81241918"
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="06a1a-102">Serialisierung und Metadaten</span><span class="sxs-lookup"><span data-stu-id="06a1a-102">Serialization and Metadata</span></span>

<span data-ttu-id="06a1a-103">Wenn Ihre Anwendung Objekte serialisiert und deserialisiert, müssen Sie möglicherweise Einträge zur Laufzeitanweisungsdatei (.rd.xml) hinzufügen, um sicherzustellen, dass die erforderlichen Metadaten zur Laufzeit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="06a1a-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="06a1a-104">Es gibt zwei Kategorien von Serialisierungsprogrammen, und jedes erfordert eine andere Behandlung in der Laufzeitdirektivendatei:</span><span class="sxs-lookup"><span data-stu-id="06a1a-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
- <span data-ttu-id="06a1a-105">Reflektionsbasierte Drittanbieter-Serialisierungsprogramme.</span><span class="sxs-lookup"><span data-stu-id="06a1a-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="06a1a-106">Diese erfordern Änderungen an der Laufzeitdirektivendatei und werden im nächsten Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="06a1a-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
- <span data-ttu-id="06a1a-107">Nicht-reflektionsbasierte Serialisierungsprogramme aus der. NET Framework-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="06a1a-107">Non-reflection based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="06a1a-108">Diese erfordern möglicherweise Änderungen an der Laufzeitanweisungsdatei und werden im Abschnitt [Microsoft-Serialisierungsprogramme](#Microsoft) erläutert.</span><span class="sxs-lookup"><span data-stu-id="06a1a-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>
## <a name="third-party-serializers"></a><span data-ttu-id="06a1a-109">Drittanbieter-Serialisierungsprogramme</span><span class="sxs-lookup"><span data-stu-id="06a1a-109">Third-party serializers</span></span>

 <span data-ttu-id="06a1a-110">Drittanbieter-Serialisierungsprogramme, einschließlich Newtonsoft.JSON, sind in der Regel reflektionsbasiert.</span><span class="sxs-lookup"><span data-stu-id="06a1a-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="06a1a-111">Bei einem BLOB aus serialisierten Daten werden die Felder in den Daten einem konkreten Typ durch Suchen der Felder des Zieltyps nach dem Namen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="06a1a-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="06a1a-112">Durch das Verwenden dieser Bibliotheken werden mindestens [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahmen für alle <xref:System.Type>-Objekte verursacht, die Sie in einer `List<Type>`-Auflistung serialisieren oder deserialisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="06a1a-112">At a minimum, using these libraries causes [MissingMetadataException](missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="06a1a-113">Durch fehlende Metadaten für diese Serialisierungsprogramme verursachte Probleme können am einfachsten gelöst werden, indem Sie Typen auflisten, die bei der Serialisierung unter einem einzigen Namespace verwendet werden (z. B. `App.Models`) und eine `Serialize`-Metadatenanweisung darauf anwenden:</span><span class="sxs-lookup"><span data-stu-id="06a1a-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="06a1a-114">Informationen zur im Beispiel verwendeten Syntax finden Sie unter [ \<Namespace> Element](namespace-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="06a1a-114">For information about the syntax used in the example, see [\<Namespace> Element](namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>
## <a name="microsoft-serializers"></a><span data-ttu-id="06a1a-115">Microsoft-Serialisierungsprogramme</span><span class="sxs-lookup"><span data-stu-id="06a1a-115">Microsoft serializers</span></span>

 <span data-ttu-id="06a1a-116">Obwohl die Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und <xref:System.Xml.Serialization.XmlSerializer> nicht auf Reflektion angewiesen sind, muss dennoch Code basierend auf dem Objekt, das serialisiert oder deserialisiert werden soll, generiert werden.</span><span class="sxs-lookup"><span data-stu-id="06a1a-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="06a1a-117">Die überladenen Konstruktoren für die einzelnen Serialisierungsprogramme enthalten einen <xref:System.Type> -Parameter, der angibt, welcher Typ serialisiert oder deserialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="06a1a-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="06a1a-118">Wie Sie diesen Typ im Code angeben, definiert die Aktion, die Sie ausführen müssen, wie in den nächsten beiden Abschnitten erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="06a1a-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="06a1a-119">Im Konstruktor verwendetes "typeof"-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="06a1a-119">typeof used in the constructor</span></span>

 <span data-ttu-id="06a1a-120">Wenn Sie einen Konstruktor dieser Serialisierungsklassen [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) aufrufen und den Operator "C"-Typof in den Methodenaufruf einbeziehen, **müssen Sie keine zusätzliche Arbeit erledigen.**</span><span class="sxs-lookup"><span data-stu-id="06a1a-120">If you call a constructor of these serialization classes and include the C# [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) operator in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="06a1a-121">In jedem der folgenden Aufrufe eines Serialisierungsklassenkonstruktors wird z. B. das `typeof`-Schlüsselwort als Teil des Ausdrucks verwendet, der an den Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="06a1a-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="06a1a-122">Der .NET Native-Compiler verarbeitet diesen Code automatisch.</span><span class="sxs-lookup"><span data-stu-id="06a1a-122">The .NET Native compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="06a1a-123">Außerhalb des Konstruktors verwendetes "typeof"-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="06a1a-123">typeof used outside the constructor</span></span>

 <span data-ttu-id="06a1a-124">Wenn Sie einen Konstruktor dieser Serialisierungsklassen aufrufen und den [Operator](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) "C" außerhalb des Ausdrucks verwenden, der dem Parameter des Konstruktors <xref:System.Type> bereitgestellt wird, wie im folgenden Code, kann der .NET Native-Compiler den Typ nicht auflösen:</span><span class="sxs-lookup"><span data-stu-id="06a1a-124">If you call a constructor of these serialization classes and use the C# [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) operator outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the .NET Native compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="06a1a-125">In diesem Fall müssen Sie den Typ in der Laufzeitanweisungsdatei angeben, indem Sie einen Eintrag wie den folgenden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="06a1a-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="06a1a-126">Wenn Sie einen Konstruktor wie <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> z. B. <xref:System.Type> aufrufen und ein Array zusätzlicher Objekte zum Serialisieren bereitstellen, wie im folgenden Code, kann der .NET Native-Compiler diese Typen nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="06a1a-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the .NET Native compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 <span data-ttu-id="06a1a-127">Sie müssen der Laufzeitanweisungsdatei Einträge wie folgenden für jeden Typ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="06a1a-127">You must add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 <span data-ttu-id="06a1a-128">Informationen zur im Beispiel verwendeten Syntax [ \<](type-element-net-native.md)finden Sie unter Typ> Element .</span><span class="sxs-lookup"><span data-stu-id="06a1a-128">For information about the syntax used in the example, see [\<Type> Element](type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a1a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06a1a-129">See also</span></span>

- [<span data-ttu-id="06a1a-130">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="06a1a-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="06a1a-131">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="06a1a-131">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="06a1a-132">\<Typ> Element</span><span class="sxs-lookup"><span data-stu-id="06a1a-132">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="06a1a-133">\<Namespace> Element</span><span class="sxs-lookup"><span data-stu-id="06a1a-133">\<Namespace> Element</span></span>](namespace-element-net-native.md)
