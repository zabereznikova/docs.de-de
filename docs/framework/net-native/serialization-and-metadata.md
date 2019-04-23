---
title: Serialisierung und Metadaten
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c82d32fe5b1e62a19ff5e2920c5943f1303b2d64
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207031"
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="b52f0-102">Serialisierung und Metadaten</span><span class="sxs-lookup"><span data-stu-id="b52f0-102">Serialization and Metadata</span></span>
<span data-ttu-id="b52f0-103">Wenn Ihre Anwendung Objekte serialisiert und deserialisiert, müssen Sie möglicherweise Einträge zur Laufzeitanweisungsdatei (.rd.xml) hinzufügen, um sicherzustellen, dass die erforderlichen Metadaten zur Laufzeit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b52f0-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="b52f0-104">Es gibt zwei Kategorien von Serialisierungsprogrammen, und jedes erfordert eine andere Behandlung in der Laufzeitdirektivendatei:</span><span class="sxs-lookup"><span data-stu-id="b52f0-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
-   <span data-ttu-id="b52f0-105">Reflektionsbasierte Drittanbieter-Serialisierungsprogramme.</span><span class="sxs-lookup"><span data-stu-id="b52f0-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="b52f0-106">Diese erfordern Änderungen an der Laufzeitdirektivendatei und werden im nächsten Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="b52f0-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
-   <span data-ttu-id="b52f0-107">Nicht-reflektionsbasierte Serialisierungsprogramme aus der. NET Framework-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b52f0-107">Non-reflection based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="b52f0-108">Diese erfordern möglicherweise Änderungen an der Laufzeitanweisungsdatei und werden im Abschnitt [Microsoft-Serialisierungsprogramme](#Microsoft) erläutert.</span><span class="sxs-lookup"><span data-stu-id="b52f0-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>   
## <a name="third-party-serializers"></a><span data-ttu-id="b52f0-109">Drittanbieter-Serialisierungsprogramme</span><span class="sxs-lookup"><span data-stu-id="b52f0-109">Third-party serializers</span></span>  
 <span data-ttu-id="b52f0-110">Drittanbieter-Serialisierungsprogramme, einschließlich Newtonsoft.JSON, sind in der Regel reflektionsbasiert.</span><span class="sxs-lookup"><span data-stu-id="b52f0-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="b52f0-111">Bei einem BLOB aus serialisierten Daten werden die Felder in den Daten einem konkreten Typ durch Suchen der Felder des Zieltyps nach dem Namen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b52f0-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="b52f0-112">Durch das Verwenden dieser Bibliotheken werden mindestens [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)-Ausnahmen für alle <xref:System.Type>-Objekte verursacht, die Sie in einer `List<Type>`-Auflistung serialisieren oder deserialisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b52f0-112">At a minimum, using these libraries causes [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="b52f0-113">Durch fehlende Metadaten für diese Serialisierungsprogramme verursachte Probleme können am einfachsten gelöst werden, indem Sie Typen auflisten, die bei der Serialisierung unter einem einzigen Namespace verwendet werden (z. B. `App.Models`) und eine `Serialize`-Metadatenanweisung darauf anwenden:</span><span class="sxs-lookup"><span data-stu-id="b52f0-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="b52f0-114">Informationen zur im Beispiel verwendeten Syntax finden Sie unter [\<Namespace>-Element](../../../docs/framework/net-native/namespace-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="b52f0-114">For information about the syntax used in the example, see [\<Namespace> Element](../../../docs/framework/net-native/namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>   
## <a name="microsoft-serializers"></a><span data-ttu-id="b52f0-115">Microsoft-Serialisierungsprogramme</span><span class="sxs-lookup"><span data-stu-id="b52f0-115">Microsoft serializers</span></span>  
 <span data-ttu-id="b52f0-116">Obwohl die Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und <xref:System.Xml.Serialization.XmlSerializer> nicht auf Reflektion angewiesen sind, muss dennoch Code basierend auf dem Objekt, das serialisiert oder deserialisiert werden soll, generiert werden.</span><span class="sxs-lookup"><span data-stu-id="b52f0-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="b52f0-117">Die überladenen Konstruktoren für die einzelnen Serialisierungsprogramme enthalten einen <xref:System.Type> -Parameter, der angibt, welcher Typ serialisiert oder deserialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b52f0-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="b52f0-118">Wie Sie diesen Typ im Code angeben, definiert die Aktion, die Sie ausführen müssen, wie in den nächsten beiden Abschnitten erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="b52f0-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="b52f0-119">Im Konstruktor verwendetes "typeof"-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="b52f0-119">typeof used in the constructor</span></span>  
 <span data-ttu-id="b52f0-120">Wenn Sie einen Konstruktor dieser Serialisierungsklassen aufrufen und das C#-[typeof](~/docs/csharp/language-reference/keywords/typeof.md)-Schlüsselwort in den Methodenaufruf einschließen, **sind keine weiteren Schritte erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b52f0-120">If you call a constructor of these serialization classes and include the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="b52f0-121">In jedem der folgenden Aufrufe eines Serialisierungsklassenkonstruktors wird z. B. das `typeof`-Schlüsselwort als Teil des Ausdrucks verwendet, der an den Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b52f0-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="b52f0-122">Der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Compiler verarbeitet diesen Code automatisch.</span><span class="sxs-lookup"><span data-stu-id="b52f0-122">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="b52f0-123">Außerhalb des Konstruktors verwendetes "typeof"-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="b52f0-123">typeof used outside the constructor</span></span>  
 <span data-ttu-id="b52f0-124">Wenn Sie einen Konstruktor dieser Serialisierungsklassen aufrufen und das C#-[typeof](~/docs/csharp/language-reference/keywords/typeof.md)-Schlüsselwort außerhalb des Ausdrucks verwenden, der für den <xref:System.Type>-Parameter des Konstruktors wie im folgenden Code bereitgestellt wird, kann der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Compiler den Typ nicht auflösen:</span><span class="sxs-lookup"><span data-stu-id="b52f0-124">If you call a constructor of these serialization classes and use the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="b52f0-125">In diesem Fall müssen Sie den Typ in der Laufzeitanweisungsdatei angeben, indem Sie einen Eintrag wie den folgenden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b52f0-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="b52f0-126">Wenn Sie einen Konstruktor wie z. B. <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> aufrufen und ein Array mit zusätzlichen <xref:System.Type>-Objekten zum Serialisieren wie im folgenden Code bereitstellen, kann der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Compiler diese Typen nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="b52f0-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 <span data-ttu-id="b52f0-127">Sie müssen der Laufzeitanweisungsdatei Einträge wie folgenden für jeden Typ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b52f0-127">You must add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 <span data-ttu-id="b52f0-128">Informationen zur im Beispiel verwendeten Syntax finden Sie unter [\<Type>-Element](../../../docs/framework/net-native/type-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="b52f0-128">For information about the syntax used in the example, see [\<Type> Element](../../../docs/framework/net-native/type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52f0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b52f0-129">See also</span></span>

- [<span data-ttu-id="b52f0-130">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="b52f0-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b52f0-131">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b52f0-131">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="b52f0-132">\<Type >-Element</span><span class="sxs-lookup"><span data-stu-id="b52f0-132">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)
- [<span data-ttu-id="b52f0-133">\<Namespace>-Element</span><span class="sxs-lookup"><span data-stu-id="b52f0-133">\<Namespace> Element</span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)
