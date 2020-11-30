---
title: "\"XmlSchemaSet\" zur Kompilierung von Schemata"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c4b175-3170-4071-9d60-dd5a42f79b54
ms.openlocfilehash: 4501f3dde8d402bd318332dfe9b2209b3febea71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723362"
---
# <a name="xmlschemaset-for-schema-compilation"></a><span data-ttu-id="575d1-102">"XmlSchemaSet" zur Kompilierung von Schemata</span><span class="sxs-lookup"><span data-stu-id="575d1-102">XmlSchemaSet for Schema Compilation</span></span>

<span data-ttu-id="575d1-103">Beschreibt das <xref:System.Xml.Schema.XmlSchemaSet>, bei dem es sich um einen Cache handelt, in dem XSD-Schemata (XML Schema Definition Language) gespeichert und validiert werden können.</span><span class="sxs-lookup"><span data-stu-id="575d1-103">Describes the <xref:System.Xml.Schema.XmlSchemaSet>, a cache where XML Schema definition language (XSD) schemas can be stored and validated.</span></span>  
  
## <a name="the-xmlschemaset-class"></a><span data-ttu-id="575d1-104">Die XmlSchemaSet-Klasse</span><span class="sxs-lookup"><span data-stu-id="575d1-104">The XmlSchemaSet Class</span></span>  

 <span data-ttu-id="575d1-105">Beim <xref:System.Xml.Schema.XmlSchemaSet> handelt es sich um einen Cache, in dem XSD-Schemata (XML Schema Definition Language) gespeichert und validiert werden können.</span><span class="sxs-lookup"><span data-stu-id="575d1-105">The <xref:System.Xml.Schema.XmlSchemaSet> is a cache where XML Schema definition language (XSD) schemas can be stored and validated.</span></span>  
  
 <span data-ttu-id="575d1-106">In <xref:System.Xml?displayProperty=nameWithType>, Version 1.0, wurden XML-Schemata als Schemabibliothek in eine <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse geladen.</span><span class="sxs-lookup"><span data-stu-id="575d1-106">In <xref:System.Xml?displayProperty=nameWithType> version 1.0, XML schemas were loaded into an <xref:System.Xml.Schema.XmlSchemaCollection> class as a library of schemas.</span></span> <span data-ttu-id="575d1-107">In <xref:System.Xml?displayProperty=nameWithType>, Version 2.0, sind die <xref:System.Xml.XmlValidatingReader>-Klasse und die <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse veraltet und wurden durch die <xref:System.Xml.XmlReader.Create%2A>-Methoden bzw. die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse ersetzt.</span><span class="sxs-lookup"><span data-stu-id="575d1-107">In <xref:System.Xml?displayProperty=nameWithType> version 2.0, the <xref:System.Xml.XmlValidatingReader> and the <xref:System.Xml.Schema.XmlSchemaCollection> classes are obsolete, and have been replaced by the <xref:System.Xml.XmlReader.Create%2A> methods, and the <xref:System.Xml.Schema.XmlSchemaSet> class respectively.</span></span>  
  
 <span data-ttu-id="575d1-108">Das <xref:System.Xml.Schema.XmlSchemaSet> wurde eingeführt, um eine Reihe von Problemen einschließlich der Kompatibilität mit Standards, der Leistungsfähigkeit und des veralteten Microsoft XDR-Schemaformats (XML-Data Reduced) zu beheben.</span><span class="sxs-lookup"><span data-stu-id="575d1-108">The <xref:System.Xml.Schema.XmlSchemaSet> has been introduced to fix a number of issues including standards compatibility, performance, and the obsolete Microsoft XML-Data Reduced (XDR) schema format.</span></span>  
  
 <span data-ttu-id="575d1-109">Es folgt ein Vergleich zwischen der <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse und der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="575d1-109">The following is a comparison between the <xref:System.Xml.Schema.XmlSchemaCollection> class and the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span>  
  
|<span data-ttu-id="575d1-110">XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="575d1-110">XmlSchemaCollection</span></span>|<span data-ttu-id="575d1-111">XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="575d1-111">XmlSchemaSet</span></span>|  
|-------------------------|------------------|  
|<span data-ttu-id="575d1-112">Unterstützt Microsoft XDR-Schemata und XML-Schemata des W3C.</span><span class="sxs-lookup"><span data-stu-id="575d1-112">Supports Microsoft XDR and W3C XML schemas.</span></span>|<span data-ttu-id="575d1-113">Unterstützt nur XML-Schemata des W3C.</span><span class="sxs-lookup"><span data-stu-id="575d1-113">Only supports W3C XML schemas.</span></span>|  
|<span data-ttu-id="575d1-114">Die Schemata werden beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>-Methode kompiliert.</span><span class="sxs-lookup"><span data-stu-id="575d1-114">Schemas are compiled when the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method is called.</span></span>|<span data-ttu-id="575d1-115">Die Schemata werden beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="575d1-115">Schemas are not compiled when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method is called.</span></span> <span data-ttu-id="575d1-116">Dadurch wird die Leistungsfähigkeit während der Erstellung der Schemabibliothek erhöht.</span><span class="sxs-lookup"><span data-stu-id="575d1-116">This provides a performance improvement during creation of the schema library.</span></span>|  
|<span data-ttu-id="575d1-117">Von jedem Schema wird eine einzelne kompilierte Version erstellt, was zu "Schemainseln" führen kann.</span><span class="sxs-lookup"><span data-stu-id="575d1-117">Each schema generates an individual compiled version that can result in "schema islands."</span></span> <span data-ttu-id="575d1-118">Folglich werden alle Includes und Importe nur innerhalb dieses Schemas zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="575d1-118">As a result, all includes and imports are scoped only within that schema.</span></span>|<span data-ttu-id="575d1-119">Kompilierte Schemata erstellen ein einzelnes logisches Schema, eine "Gruppe" von Schemata.</span><span class="sxs-lookup"><span data-stu-id="575d1-119">Compiled schemas generate a single logical schema, a "set" of schemas.</span></span> <span data-ttu-id="575d1-120">Alle importierten Schemata innerhalb eines Schemas, die der Gruppe hinzugefügt werden, werden der Gruppe selbst direkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="575d1-120">Any imported schemas within a schema that are added to the set are directly added to the set themselves.</span></span> <span data-ttu-id="575d1-121">Daher sind alle Typen für alle Schemata verfügbar.</span><span class="sxs-lookup"><span data-stu-id="575d1-121">This means that all types are available to all schemas.</span></span>|  
|<span data-ttu-id="575d1-122">Es kann nur ein Schema für einen bestimmten Zielnamespace in der Auflistung vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="575d1-122">Only one schema for a particular target namespace can exist in the collection.</span></span>|<span data-ttu-id="575d1-123">Es können mehrere Schemata für denselben Zielnamespace hinzugefügt werden, wenn keine Typenkonflikte auftreten.</span><span class="sxs-lookup"><span data-stu-id="575d1-123">Multiple schemas for the same target namespace can be added as long as there are no type conflicts.</span></span>|  
  
## <a name="migrating-to-the-xmlschemaset"></a><span data-ttu-id="575d1-124">Migrieren zum "XmlSchemaSet"</span><span class="sxs-lookup"><span data-stu-id="575d1-124">Migrating to the XmlSchemaSet</span></span>  

 <span data-ttu-id="575d1-125">Im folgenden Codebeispiel ist eine Anleitung zum Migrieren von der veralteten <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse zur neuen <xref:System.Xml.Schema.XmlSchemaSet>-Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="575d1-125">The following code example provides a guide to migrating to the new <xref:System.Xml.Schema.XmlSchemaSet> class from the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> class.</span></span> <span data-ttu-id="575d1-126">Im Codebeispiel werden die folgenden Hauptunterschiede zwischen den beiden Klassen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="575d1-126">The code example illustrates the following major differences between the two classes.</span></span>  
  
- <span data-ttu-id="575d1-127">Im Gegensatz zur <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse werden die Schemata beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode von <xref:System.Xml.Schema.XmlSchemaSet> nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="575d1-127">Unlike the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaCollection> class, schemas are not compiled when calling the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-128">Die <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode von <xref:System.Xml.Schema.XmlSchemaSet> wird im Beispielcode explizit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="575d1-128">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is explicitly called in the example code.</span></span>  
  
- <span data-ttu-id="575d1-129">Wenn Sie ein <xref:System.Xml.Schema.XmlSchemaSet> durchlaufen möchten, verwenden Sie die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="575d1-129">To iterate over an <xref:System.Xml.Schema.XmlSchemaSet>, you must use the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="575d1-130">Nachfolgend ist ein Beispiel des veralteten <xref:System.Xml.Schema.XmlSchemaCollection>-Codes angegeben.</span><span class="sxs-lookup"><span data-stu-id="575d1-130">The following is the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> code example.</span></span>  
  
```vb  
Dim schemaCollection As XmlSchemaCollection = New XmlSchemaCollection()  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema in schemaCollection  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaCollection schemaCollection = new XmlSchemaCollection();  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
  
foreach(XmlSchema schema in schemaCollection)  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
 <span data-ttu-id="575d1-131">Nachfolgend ist ein Beispiel des entsprechenden <xref:System.Xml.Schema.XmlSchemaSet>-Codes angegeben.</span><span class="sxs-lookup"><span data-stu-id="575d1-131">The following is the equivalent <xref:System.Xml.Schema.XmlSchemaSet> code example.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim schema As XmlSchema  
  
For Each schema in schemaSet.Schemas()  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
foreach(XmlSchema schema in schemaSet.Schemas())  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
## <a name="adding-and-retrieving-schemas"></a><span data-ttu-id="575d1-132">Hinzufügen und Abrufen von Schemata</span><span class="sxs-lookup"><span data-stu-id="575d1-132">Adding and Retrieving Schemas</span></span>  

 <span data-ttu-id="575d1-133">Schemata werden einem <xref:System.Xml.Schema.XmlSchemaSet> mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode von <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="575d1-133">Schemas are added to an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-134">Wenn ein Schema einem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt wird, wird es einem Namespace-URI zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="575d1-134">When a schema is added to an <xref:System.Xml.Schema.XmlSchemaSet>, it is associated with a target namespace URI.</span></span> <span data-ttu-id="575d1-135">Der Zielnamespace-URI kann als Parameter für die <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode angegeben werden. Wenn kein Namespace angegeben wurde, verwendet das <xref:System.Xml.Schema.XmlSchemaSet> den im Schema angegebenen Zielnamespace.</span><span class="sxs-lookup"><span data-stu-id="575d1-135">The target namespace URI can either be specified as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method or if no target namespace is specified, the <xref:System.Xml.Schema.XmlSchemaSet> uses the target namespace defined in the schema.</span></span>  
  
 <span data-ttu-id="575d1-136">Schemata werden mithilfe der <xref:System.Xml.Schema.XmlSchemaSet>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> aus dem <xref:System.Xml.Schema.XmlSchemaSet> abgerufen.</span><span class="sxs-lookup"><span data-stu-id="575d1-136">Schemas are retrieved from an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-137">Mit der <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet> können Sie die im <xref:System.Xml.Schema.XmlSchema> enthaltenen <xref:System.Xml.Schema.XmlSchemaSet>-Objekte durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="575d1-137">The <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> allows you to iterate over the <xref:System.Xml.Schema.XmlSchema> objects contained in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-138">Die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft gibt entweder alle im<xref:System.Xml.Schema.XmlSchema> enthaltenen <xref:System.Xml.Schema.XmlSchemaSet>-Objekte zurück. Ansonsten, wenn ein Parameter für den Zielnamespace angegeben wurde, werden alle zu diesem Zielnamespace gehörenden <xref:System.Xml.Schema.XmlSchema>-Objekte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="575d1-138">The <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property either returns all the <xref:System.Xml.Schema.XmlSchema> objects contained in the <xref:System.Xml.Schema.XmlSchemaSet>, or, given a target namespace parameter, returns all the <xref:System.Xml.Schema.XmlSchema> objects that belong to the target namespace.</span></span> <span data-ttu-id="575d1-139">Wenn `null` als Parameter für den Zielnamespace angegeben wurde, gibt die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft alle Schemata ohne Namespace zurück.</span><span class="sxs-lookup"><span data-stu-id="575d1-139">If `null` is specified as the target namespace parameter, the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property returns all schemas without a namespace.</span></span>  
  
 <span data-ttu-id="575d1-140">Im folgenden Beispiel wird einem `books.xsd` das `http://www.contoso.com/books`-Schema im <xref:System.Xml.Schema.XmlSchemaSet>-Namespace hinzugefügt. Außerdem werden alle Schemas, die zum `http://www.contoso.com/books`-Namespace gehören, aus dem <xref:System.Xml.Schema.XmlSchemaSet> abgerufen und in die <xref:System.Console> geschrieben.</span><span class="sxs-lookup"><span data-stu-id="575d1-140">The following example adds the `books.xsd` schema in the `http://www.contoso.com/books` namespace to an <xref:System.Xml.Schema.XmlSchemaSet>, retrieves all schemas that belong to the `http://www.contoso.com/books` namespace from the <xref:System.Xml.Schema.XmlSchemaSet>, and then writes those schemas to the <xref:System.Console>.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas("http://www.contoso.com/books")  
  
   schema.Write(Console.Out)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas("http://www.contoso.com/books"))  
{  
   schema.Write(Console.Out);  
}  
```  
  
 <span data-ttu-id="575d1-141">Weitere Informationen über das Hinzufügen und Abrufen von Schemata aus einem <xref:System.Xml.Schema.XmlSchemaSet>-Objekt finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode und zur <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="575d1-141">For more information about adding and retrieving schemas from an <xref:System.Xml.Schema.XmlSchemaSet> object, see the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method and the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property reference documentation.</span></span>  
  
## <a name="compiling-schemas"></a><span data-ttu-id="575d1-142">Kompilieren von Schemata</span><span class="sxs-lookup"><span data-stu-id="575d1-142">Compiling Schemas</span></span>  

 <span data-ttu-id="575d1-143">In einem <xref:System.Xml.Schema.XmlSchemaSet> befindliche Schemata werden von der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> in ein logisches Schema kompiliert.</span><span class="sxs-lookup"><span data-stu-id="575d1-143">Schemas in an <xref:System.Xml.Schema.XmlSchemaSet> are compiled into one logical schema by the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="575d1-144">Im Gegensatz zur veralteten <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse werden die Schemata beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="575d1-144">Unlike the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> class, schemas are not compiled when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method is called.</span></span>  
  
 <span data-ttu-id="575d1-145">Wenn die <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode erfolgreich ausgeführt wird, wird die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet> auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="575d1-145">If the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method executes successfully, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="575d1-146">Die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft wird nicht beeinflusst, wenn Schemata im <xref:System.Xml.Schema.XmlSchemaSet> bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="575d1-146">The <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property is not affected if schemas are edited while in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-147">Updates der einzelnen Schemata im <xref:System.Xml.Schema.XmlSchemaSet> werden nicht nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="575d1-147">Updates of the individual schemas in the <xref:System.Xml.Schema.XmlSchemaSet> are not tracked.</span></span> <span data-ttu-id="575d1-148">Folglich kann die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft `true` sein, obwohl eines der im <xref:System.Xml.Schema.XmlSchemaSet> enthaltenen Schemata veraltet ist, wenn keine Schemata aus dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt oder entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="575d1-148">As a result, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property can be `true` even though one of the schemas contained in the <xref:System.Xml.Schema.XmlSchemaSet> has been altered, as long as no schemas were added or removed from the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="575d1-149">Im folgenden Beispiel wird die `books.xsd`-Datei dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt und anschließend eine <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="575d1-149">The following example adds the `books.xsd` file to the <xref:System.Xml.Schema.XmlSchemaSet> and then calls the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
schemaSet.Compile()  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
schemaSet.Compile();  
```  
  
 <span data-ttu-id="575d1-150">Weitere Informationen über das Kompilieren von Schemata in einem <xref:System.Xml.Schema.XmlSchemaSet> finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="575d1-150">For more information about compiling schemas in an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method reference documentation.</span></span>  
  
## <a name="reprocessing-schemas"></a><span data-ttu-id="575d1-151">Wiederverarbeiten von Schemata</span><span class="sxs-lookup"><span data-stu-id="575d1-151">Reprocessing Schemas</span></span>  

 <span data-ttu-id="575d1-152">Beim Wiederverarbeiten eines Schemas in einem <xref:System.Xml.Schema.XmlSchemaSet> werden alle Wiederverarbeitungsschritte durchgeführt, die beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> für ein Schema durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="575d1-152">Reprocessing a schema in an <xref:System.Xml.Schema.XmlSchemaSet> performs all the preprocessing steps performed on a schema when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called.</span></span> <span data-ttu-id="575d1-153">Wenn die <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode erfolgreich aufgerufen wurde, wird die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet> auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="575d1-153">If the call to the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method is successful, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> is set to `false`.</span></span>  
  
 <span data-ttu-id="575d1-154">Die <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode sollte verwendet werden, wenn ein Schema im <xref:System.Xml.Schema.XmlSchemaSet> geändert wurde, nachdem von <xref:System.Xml.Schema.XmlSchemaSet> die Kompilierung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="575d1-154">The <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method should be used when a schema in the <xref:System.Xml.Schema.XmlSchemaSet> has been modified after the <xref:System.Xml.Schema.XmlSchemaSet> has performed compilation.</span></span>  
  
 <span data-ttu-id="575d1-155">Im folgenden Beispiel wird die Wiederverarbeitung eines Schemas dargestellt, das dem <xref:System.Xml.Schema.XmlSchemaSet> mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="575d1-155">The following example illustrates reprocessing a schema added to the <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method.</span></span> <span data-ttu-id="575d1-156">Nachdem das <xref:System.Xml.Schema.XmlSchemaSet> mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode kompiliert und das dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügte Schema geändert wurde, wird die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft auf `true` festgelegt, obwohl ein Schema im <xref:System.Xml.Schema.XmlSchemaSet> geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="575d1-156">After the <xref:System.Xml.Schema.XmlSchemaSet> is compiled using the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method, and the schema added to the <xref:System.Xml.Schema.XmlSchemaSet> is modified, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property is set to `true` even though a schema in the <xref:System.Xml.Schema.XmlSchemaSet> has been modified.</span></span> <span data-ttu-id="575d1-157">Beim Aufrufen der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode werden alle von der <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode durchgeführten Wiederverarbeitungsschritte ausgeführt, und die <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>-Eigenschaft wird auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="575d1-157">Calling the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method performs all the preprocessing performed by the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method, and sets the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property to `false`.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
Dim schema As XmlSchema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim element As XmlSchemaElement = New XmlSchemaElement()  
schema.Items.Add(element)  
element.Name = "book"  
element.SchemaTypeName = New XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema")  
  
schemaSet.Reprocess(schema)  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
XmlSchema schema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
XmlSchemaElement element = new XmlSchemaElement();  
schema.Items.Add(element);  
element.Name = "book";  
element.SchemaTypeName = new XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema");  
  
schemaSet.Reprocess(schema);  
```  
  
 <span data-ttu-id="575d1-158">Weitere Informationen über das Wiederverarbeiten eines Schemas in einem <xref:System.Xml.Schema.XmlSchemaSet> finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="575d1-158">For more information about reprocessing a schema in an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method reference documentation.</span></span>  
  
## <a name="checking-for-a-schema"></a><span data-ttu-id="575d1-159">Suche nach einem Schema</span><span class="sxs-lookup"><span data-stu-id="575d1-159">Checking for a Schema</span></span>  

 <span data-ttu-id="575d1-160">Sie können die <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> verwenden, um festzustellen ob in einem <xref:System.Xml.Schema.XmlSchemaSet> ein Schema enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="575d1-160">You can use the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> to check if a schema is contained within an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-161">Die <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode sucht entweder nach einem Zielnamespace oder einem <xref:System.Xml.Schema.XmlSchema>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="575d1-161">The <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method takes either a target namespace or an <xref:System.Xml.Schema.XmlSchema> object to check for.</span></span> <span data-ttu-id="575d1-162">In beiden Fällen gibt die <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode `true` zurück, wenn im <xref:System.Xml.Schema.XmlSchemaSet> ein Schema enthalten ist. Andernfalls gibt sie `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="575d1-162">In either case, the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method returns `true` if the schema is contained within the <xref:System.Xml.Schema.XmlSchemaSet>; otherwise, it returns `false`.</span></span>  
  
 <span data-ttu-id="575d1-163">Weitere Informationen über das Suchen nach einem Schema finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="575d1-163">For more information about checking for a schema, see the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method reference documentation.</span></span>  
  
## <a name="removing-schemas"></a><span data-ttu-id="575d1-164">Entfernen von Schemata</span><span class="sxs-lookup"><span data-stu-id="575d1-164">Removing Schemas</span></span>  

 <span data-ttu-id="575d1-165">Schemata werden mithilfe der <xref:System.Xml.Schema.XmlSchemaSet>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> aus einem <xref:System.Xml.Schema.XmlSchemaSet> entfernt.</span><span class="sxs-lookup"><span data-stu-id="575d1-165">Schemas are removed from an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> and <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-166">Die <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>-Methode entfernt das angegebene Schema aus dem <xref:System.Xml.Schema.XmlSchemaSet>, wohingegen die <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>-Methode das angegebene Schema und alle aus dem <xref:System.Xml.Schema.XmlSchemaSet> importierten Schemata entfernt.</span><span class="sxs-lookup"><span data-stu-id="575d1-166">The <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> method removes the specified schema from the <xref:System.Xml.Schema.XmlSchemaSet>, while the <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> method removes the specified schema and all the schemas it imports from the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="575d1-167">Im folgenden Beispiel wird das Hinzufügen mehrerer Schemata zu einem <xref:System.Xml.Schema.XmlSchemaSet> und die anschließende Verwendung der <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>-Methode zum Entfernen eines der Schemata und aller von ihr importierten Schemata veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="575d1-167">The following example illustrates adding multiple schemas to an <xref:System.Xml.Schema.XmlSchemaSet>, then using the <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> method to remove one of the schemas and all the schemas it imports.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas()  
  
   If schema.TargetNamespace = "http://www.contoso.com/music" Then  
      schemaSet.RemoveRecursive(schema)  
   End If  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas())  
{  
   if (schema.TargetNamespace == "http://www.contoso.com/music")  
   {  
      schemaSet.RemoveRecursive(schema);  
   }  
}  
```  
  
 <span data-ttu-id="575d1-168">Weitere Informationen über das Entfernen von Schemata aus einem <xref:System.Xml.Schema.XmlSchemaSet> finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>-Methode und zur <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="575d1-168">For more information about removing schemas from an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> and <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> methods reference documentation.</span></span>  
  
## <a name="schema-resolution-and-xsimport"></a><span data-ttu-id="575d1-169">Schemaauflösung und „xs:import“</span><span class="sxs-lookup"><span data-stu-id="575d1-169">Schema Resolution and xs:import</span></span>  

 <span data-ttu-id="575d1-170">In den folgenden Beispielen wird die Verhaltensweise des <xref:System.Xml.Schema.XmlSchemaSet> beim Importieren von Schemata beschrieben, wenn in einem <xref:System.Xml.Schema.XmlSchemaSet> mehrere Schemata für einen angegebenen Namespace vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="575d1-170">The following examples describe the <xref:System.Xml.Schema.XmlSchemaSet> behavior for importing schemas when multiple schemas for a given namespace exist in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="575d1-171">Betrachten Sie beispielsweise ein <xref:System.Xml.Schema.XmlSchemaSet>, das mehrere Schemata für den `http://www.contoso.com`-Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="575d1-171">For example, consider an <xref:System.Xml.Schema.XmlSchemaSet> that contains multiple schemas for the `http://www.contoso.com` namespace.</span></span> <span data-ttu-id="575d1-172">Ein Schema mit der folgenden `xs:import`-Anweisung wird dem <xref:System.Xml.Schema.XmlSchemaSet> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="575d1-172">A schema with the following `xs:import` directive is added to the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
```xml  
<xs:import namespace="http://www.contoso.com" schemaLocation="http://www.contoso.com/schema.xsd" />  
```  
  
 <span data-ttu-id="575d1-173">Das <xref:System.Xml.Schema.XmlSchemaSet> versucht, ein Schema für den `http://www.contoso.com`-Namespace durch Laden aus der URL `http://www.contoso.com/schema.xsd` zu importieren.</span><span class="sxs-lookup"><span data-stu-id="575d1-173">The <xref:System.Xml.Schema.XmlSchemaSet> attempts to import a schema for the `http://www.contoso.com` namespace by loading it from the `http://www.contoso.com/schema.xsd` URL.</span></span> <span data-ttu-id="575d1-174">Im Importschema sind nur die Schemadeklaration und die im Schemadokument deklarierten Typen verfügbar, obwohl im `http://www.contoso.com` andere Schemadokumente für den <xref:System.Xml.Schema.XmlSchemaSet>-Namespace vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="575d1-174">Only the schema declaration and types declared in the schema document are available in the importing schema, even though there are other schema documents for the `http://www.contoso.com` namespace in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-175">Wenn die `schema.xsd`-Datei nicht unter der URL `http://www.contoso.com/schema.xsd` gefunden werden kann, wird kein Schema für den `http://www.contoso.com`-Namespace in das Importschema importiert.</span><span class="sxs-lookup"><span data-stu-id="575d1-175">If the `schema.xsd` file cannot be located at the `http://www.contoso.com/schema.xsd` URL, no schema for the `http://www.contoso.com` namespace is imported into the importing schema.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="575d1-176">Validierung von XML-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="575d1-176">Validating XML Documents</span></span>  

 <span data-ttu-id="575d1-177">XML-Dokumente können anhand von Schemata in einem <xref:System.Xml.Schema.XmlSchemaSet> validiert werden.</span><span class="sxs-lookup"><span data-stu-id="575d1-177">XML documents can be validated against schemas in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="575d1-178">Sie validieren ein XML-Dokument, indem Sie der <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A>-Eigenschaft eines <xref:System.Xml.XmlReaderSettings>-Objekts ein Schema hinzufügen oder indem Sie der <xref:System.Xml.XmlReaderSettings.Schemas%2A>-Eigenschaft eines <xref:System.Xml.XmlReaderSettings>-Objekts eine <xref:System.Xml.Schema.XmlSchemaSet>-Klasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="575d1-178">You validate an XML document by adding a schema to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of an <xref:System.Xml.XmlReaderSettings> object, or by adding an <xref:System.Xml.Schema.XmlSchemaSet> to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of an <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="575d1-179">Das <xref:System.Xml.XmlReaderSettings>-Objekt wird anschließend von der <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse verwendet, um ein <xref:System.Xml.XmlReader>-Objekt zu erstellen und um das XML-Dokument zu validieren.</span><span class="sxs-lookup"><span data-stu-id="575d1-179">The <xref:System.Xml.XmlReaderSettings> object is then used by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class to create an <xref:System.Xml.XmlReader> object and validate the XML document.</span></span>  
  
 <span data-ttu-id="575d1-180">Weitere Informationen zum Validieren von XML-Dokumenten mithilfe einer <xref:System.Xml.Schema.XmlSchemaSet>-Klasse finden Sie unter [Validierung eines XML-Schemas (XSD) mit „XmlSchemaSet“](xml-schema-xsd-validation-with-xmlschemaset.md).</span><span class="sxs-lookup"><span data-stu-id="575d1-180">For more information about validating XML documents using an <xref:System.Xml.Schema.XmlSchemaSet>, see [XML Schema (XSD) Validation with XmlSchemaSet](xml-schema-xsd-validation-with-xmlschemaset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575d1-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="575d1-181">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>
- [<span data-ttu-id="575d1-182">„XmlSchemaSet“ zur Kompilierung von Schemata</span><span class="sxs-lookup"><span data-stu-id="575d1-182">XmlSchemaSet as a Schema Cache</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="575d1-183">Validierung eines XML-Schemas (XSD) mit „XmlSchemaSet“</span><span class="sxs-lookup"><span data-stu-id="575d1-183">XML Schema (XSD) Validation with XmlSchemaSet</span></span>](xml-schema-xsd-validation-with-xmlschemaset.md)
