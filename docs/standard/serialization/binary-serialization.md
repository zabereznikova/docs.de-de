---
title: "Binäre Serialisierung"
ms.date: 08/11/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: "5"
author: ViktorHofer
ms.author: mairaw
ms.openlocfilehash: 74ee4e21934c1e4f3fd008664b1315429dc47b37
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="binary-serialization"></a><span data-ttu-id="4af0a-102">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4af0a-102">Binary serialization</span></span>

<span data-ttu-id="4af0a-103">Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4af0a-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="4af0a-104">Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4af0a-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="4af0a-105">Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.</span><span class="sxs-lookup"><span data-stu-id="4af0a-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="4af0a-106">Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden.</span><span class="sxs-lookup"><span data-stu-id="4af0a-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="4af0a-107">Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben.</span><span class="sxs-lookup"><span data-stu-id="4af0a-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="4af0a-108">Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4af0a-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="4af0a-109">In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="4af0a-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="4af0a-110">Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4af0a-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="4af0a-111">Die Art der binären Serialisierung ermöglicht die Änderung der privaten Member innerhalb eines Objekts. Somit wird deren Status geändert. Andere Serialisierungsframeworks wie JSON.NET, die auf der öffentlichen API-Oberfläche ausgeführt werden, werden empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4af0a-111">As the nature of binary serialization allows the modification of private members inside an object and therefore changing the state of it, other serialization frameworks like JSON.NET which operate on the public API surface are recommended.</span></span>

## <a name="binary-serialization-in-net-core"></a><span data-ttu-id="4af0a-112">Binäre Serialisierung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="4af0a-112">Binary serialization in .NET Core</span></span>

<span data-ttu-id="4af0a-113">.NET Core unterstützt binäre Serialisierung mit einer Teilmenge der Typen.</span><span class="sxs-lookup"><span data-stu-id="4af0a-113">.NET Core supports binary serialization with a subset of types.</span></span> <span data-ttu-id="4af0a-114">Sie finden die Liste der unterstützten Typen im Abschnitt [Serialisierbare Typen](#serializable-types).</span><span class="sxs-lookup"><span data-stu-id="4af0a-114">You can see the list of supported types in the [Serializable types section](#serializable-types).</span></span> <span data-ttu-id="4af0a-115">Der definierte Satz von Typen kann zwischen .NET Framework 4.5.1 und höheren Versionen und .NET Core 2.0 und höheren Versionen serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4af0a-115">The defined set of types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="4af0a-116">Andere Implementierungen von .NET, z.B. Mono, werden nicht offiziell unterstützt, sollten jedoch ebenfalls funktionieren.</span><span class="sxs-lookup"><span data-stu-id="4af0a-116">Other .NET implementations, such as Mono, aren't officially supported but should also be working.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="4af0a-117">Serialisierbare Typen</span><span class="sxs-lookup"><span data-stu-id="4af0a-117">Serializable types</span></span>

- <xref:System.AggregateException?displayProperty=nameWithType>   
- <xref:System.Array?displayProperty=nameWithType>   
- <xref:System.ArraySegment%601?displayProperty=nameWithType>   
- <xref:System.Attribute?displayProperty=nameWithType>   
- <xref:System.Boolean?displayProperty=nameWithType>   
- <xref:System.Byte?displayProperty=nameWithType>   
- <xref:System.Char?displayProperty=nameWithType>   
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>   
- <xref:System.Collections.BitArray?displayProperty=nameWithType>   
- <xref:System.Collections.Comparer?displayProperty=nameWithType>   
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>   
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.Queue?displayProperty=nameWithType>   
- <xref:System.Collections.SortedList?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Stack?displayProperty=nameWithType>   
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>   
- <span data-ttu-id="4af0a-118"><xref:System.DBNull?displayProperty=nameWithType>(verfügbar in .NET Core 2.0.2 und höher)</span><span class="sxs-lookup"><span data-stu-id="4af0a-118"><xref:System.DBNull?displayProperty=nameWithType> (available in .NET Core 2.0.2 and later versions)</span></span>   
- <xref:System.Data.DataSet?displayProperty=nameWithType>   
- <xref:System.Data.DataTable?displayProperty=nameWithType>   
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>   
- <xref:System.DateTime?displayProperty=nameWithType>   
- <xref:System.DateTimeOffset?displayProperty=nameWithType>   
- <xref:System.Decimal?displayProperty=nameWithType>   
- <xref:System.Double?displayProperty=nameWithType>   
- <xref:System.Drawing.Color?displayProperty=nameWithType>   
- <xref:System.Drawing.Point?displayProperty=nameWithType>   
- <xref:System.Drawing.PointF?displayProperty=nameWithType>   
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>   
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>   
- <xref:System.Drawing.Size?displayProperty=nameWithType>   
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>   
- <xref:System.Enum?displayProperty=nameWithType>   
- <xref:System.Exception?displayProperty=nameWithType>   
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>   
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>   
- <xref:System.Guid?displayProperty=nameWithType>   
- <xref:System.Int16?displayProperty=nameWithType>   
- <xref:System.Int32?displayProperty=nameWithType>   
- <xref:System.Int64?displayProperty=nameWithType>   
- <xref:System.IntPtr?displayProperty=nameWithType>   
- <xref:System.Net.Cookie?displayProperty=nameWithType>   
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>   
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>   
- <xref:System.Nullable%601?displayProperty=nameWithType>   
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>   
- <xref:System.Numerics.Complex?displayProperty=nameWithType>   
- <xref:System.Object?displayProperty=nameWithType>   
- <xref:System.SByte?displayProperty=nameWithType>   
- <xref:System.Single?displayProperty=nameWithType>   
- <xref:System.String?displayProperty=nameWithType>   
- <xref:System.StringComparer?displayProperty=nameWithType>   
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>   
- <xref:System.TimeSpan?displayProperty=nameWithType>   
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>   
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>   
- <xref:System.Tuple?displayProperty=nameWithType>   
- <xref:System.UInt16?displayProperty=nameWithType>   
- <xref:System.UInt32?displayProperty=nameWithType>   
- <xref:System.UInt64?displayProperty=nameWithType>   
- <xref:System.UIntPtr?displayProperty=nameWithType>   
- <xref:System.Uri?displayProperty=nameWithType>   
- <span data-ttu-id="4af0a-119"><xref:System.ValueTuple?displayProperty=nameWithType>(nicht serialisierbar in .NET Framework 4.7 und früheren Versionen)</span><span class="sxs-lookup"><span data-stu-id="4af0a-119"><xref:System.ValueTuple?displayProperty=nameWithType> (not serializable in .NET Framework 4.7 and earlier versions)</span></span>  
- <xref:System.ValueType?displayProperty=nameWithType>   
- <xref:System.Version?displayProperty=nameWithType>   
- <xref:System.WeakReference?displayProperty=nameWithType>   
- <xref:System.WeakReference%601?displayProperty=nameWithType>   

## <a name="in-this-section"></a><span data-ttu-id="4af0a-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4af0a-120">In this section</span></span>

 [<span data-ttu-id="4af0a-121">Serialisierungskonzepte</span><span class="sxs-lookup"><span data-stu-id="4af0a-121">Serialization Concepts</span></span>](../../../docs/standard/serialization/serialization-concepts.md)  
 <span data-ttu-id="4af0a-122">Erläutert zwei Szenarien, in denen die Serialisierung sinnvoll eingesetzt werden kann: wenn Daten im Speicher beibehalten werden sollen und wenn Objekte über Anwendungsdomänen hinweg übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4af0a-122">Discusses two scenarios where serialization is useful: when persisting data to storage and when passing objects across application domains.</span></span>  
  
 [<span data-ttu-id="4af0a-123">Einfache Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4af0a-123">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 <span data-ttu-id="4af0a-124">Beschreibt, wie die Binärdatei und SOAP-Formatierungsprogramme verwendet werden, um Objekte zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="4af0a-124">Describes how to use the binary and SOAP formatters to serialize objects.</span></span>  
  
 [<span data-ttu-id="4af0a-125">Selective Serialization</span><span class="sxs-lookup"><span data-stu-id="4af0a-125">Selective Serialization</span></span>](../../../docs/standard/serialization/selective-serialization.md)  
 <span data-ttu-id="4af0a-126">Beschreibt, wie verhindert wird, dass einige Member einer Klasse serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4af0a-126">Describes how to prevent some members of a class from being serialized.</span></span>  
  
 [<span data-ttu-id="4af0a-127">Benutzerdefinierte Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4af0a-127">Custom Serialization</span></span>](../../../docs/standard/serialization/custom-serialization.md)  
 <span data-ttu-id="4af0a-128">Beschreibt, wie mithilfe der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle die Serialisierung für eine Klasse angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="4af0a-128">Describes how to customize serialization for a class by using the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>  
  
 [<span data-ttu-id="4af0a-129">Schritte im Serialisierungsprozess</span><span class="sxs-lookup"><span data-stu-id="4af0a-129">Steps in the Serialization Process</span></span>](../../../docs/standard/serialization/steps-in-the-serialization-process.md)  
 <span data-ttu-id="4af0a-130">Beschreibt die einzelnen Serialisierungsschritte, die ausgeführt werden, wenn die <xref:System.Runtime.Serialization.Formatter.Serialize%2A>-Methode für ein Formatierungsprogramm aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4af0a-130">Describes the course of action serialization takes when the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a formatter.</span></span>  
  
 [<span data-ttu-id="4af0a-131">Versionstolerante Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4af0a-131">Version Tolerant Serialization</span></span>](../../../docs/standard/serialization/version-tolerant-serialization.md)  
 <span data-ttu-id="4af0a-132">Erklärt, wie serialisierbare Typen erstellt werden, die im Lauf der Zeit modifiziert werden können, ohne dass dies zur Folge hat, dass Anwendungen Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="4af0a-132">Explains how to create serializable types that can be modified over time without causing applications to throw exceptions.</span></span>  
  
 [<span data-ttu-id="4af0a-133">Serialisierungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4af0a-133">Serialization Guidelines</span></span>](../../../docs/standard/serialization/serialization-guidelines.md)  
 <span data-ttu-id="4af0a-134">Stellt einige allgemeine Richtlinien zur Entscheidung der Frage bereit, wann ein Objekt serialisiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="4af0a-134">Provides some general guidelines for deciding when to serialize an object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4af0a-135">Verweis</span><span class="sxs-lookup"><span data-stu-id="4af0a-135">Reference</span></span>  
 <xref:System.Runtime.Serialization>  
 <span data-ttu-id="4af0a-136">Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="4af0a-136">Contains classes that can be used for serializing and deserializing objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4af0a-137">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4af0a-137">Related sections</span></span>  
 [<span data-ttu-id="4af0a-138">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4af0a-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 <span data-ttu-id="4af0a-139">Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4af0a-139">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>  
  
 [<span data-ttu-id="4af0a-140">Sicherheit und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4af0a-140">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)  
 <span data-ttu-id="4af0a-141">Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.</span><span class="sxs-lookup"><span data-stu-id="4af0a-141">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>  
  
 [<span data-ttu-id="4af0a-142">Remoteobjekte</span><span class="sxs-lookup"><span data-stu-id="4af0a-142">Remote Objects</span></span>](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58)  
 <span data-ttu-id="4af0a-143">Beschreibt die verschiedenen Kommunikationsverfahren, die in .NET&#160;Framework für die Remotekommunikation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4af0a-143">Describes the various communications methods available in the .NET Framework for remote communications.</span></span>  
  
 [<span data-ttu-id="4af0a-144">Mithilfe von ASP.NET und XML-Webdiensteclients erstellte XML-Webdienste</span><span class="sxs-lookup"><span data-stu-id="4af0a-144">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 <span data-ttu-id="4af0a-145">Stellt Themen bereit, die beschreiben und erklären, wie mit ASP.NET erstellte XML-Webdienste programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="4af0a-145">Provides topics that describe and explain how to program XML Web services created using ASP.NET.</span></span>
