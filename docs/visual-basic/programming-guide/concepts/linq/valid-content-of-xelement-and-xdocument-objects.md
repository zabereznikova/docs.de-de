---
title: "Gültiger Inhalt von XElement- und XDocument-Objekte2 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ecdcd4c2c0ec61cf248c9e210d42abb750e0546b
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="3a18b-102">Gültiger Inhalt von XElement- und XDocument-Objekten</span><span class="sxs-lookup"><span data-stu-id="3a18b-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="3a18b-103">In diesem Thema werden die gültigen Argumente beschrieben, die an die Konstruktoren und Methoden übergeben werden können, die Sie zum Hinzufügen von Inhalt zu Elementen und Dokumenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a18b-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="3a18b-104">Gültiger Inhalt</span><span class="sxs-lookup"><span data-stu-id="3a18b-104">Valid Content</span></span>  
 <span data-ttu-id="3a18b-105">Abfragen ergeben häufig <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="3a18b-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="3a18b-106">Sie können Sammlungen von übergeben <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte, die <xref:System.Xml.Linq.XElement>Konstruktor.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3a18b-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="3a18b-107">Aus diesem Grund bietet es sich an, die Ergebnisse einer Abfrage als Inhalt an Methoden und Konstruktoren zu übergeben, mit denen Sie XML-Strukturen auffüllen können.</span><span class="sxs-lookup"><span data-stu-id="3a18b-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="3a18b-108">Beim Hinzufügen einfachen Inhalts können dieser Methode verschiedene Typen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="3a18b-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="3a18b-109">Gültige Typen sind:</span><span class="sxs-lookup"><span data-stu-id="3a18b-109">Valid types include the following:</span></span>  
  
-   <span data-ttu-id="3a18b-110"><xref:System.String></xref:System.String></span><span class="sxs-lookup"><span data-stu-id="3a18b-110"><xref:System.String></span></span>  
  
-   <span data-ttu-id="3a18b-111"><xref:System.Double></xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="3a18b-111"><xref:System.Double></span></span>  
  
-   <span data-ttu-id="3a18b-112"><xref:System.Single></xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="3a18b-112"><xref:System.Single></span></span>  
  
-   <span data-ttu-id="3a18b-113"><xref:System.Decimal></xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="3a18b-113"><xref:System.Decimal></span></span>  
  
-   <span data-ttu-id="3a18b-114"><xref:System.Boolean></xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="3a18b-114"><xref:System.Boolean></span></span>  
  
-   <span data-ttu-id="3a18b-115"><xref:System.DateTime></xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="3a18b-115"><xref:System.DateTime></span></span>  
  
-   <span data-ttu-id="3a18b-116"><xref:System.TimeSpan></xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="3a18b-116"><xref:System.TimeSpan></span></span>  
  
-   <span data-ttu-id="3a18b-117"><xref:System.DateTimeOffset></xref:System.DateTimeOffset></span><span class="sxs-lookup"><span data-stu-id="3a18b-117"><xref:System.DateTimeOffset></span></span>  
  
-   <span data-ttu-id="3a18b-118">Alle Typen, die `Object.ToString` implementieren.</span><span class="sxs-lookup"><span data-stu-id="3a18b-118">Any type that implements `Object.ToString`.</span></span>  
  
-   <span data-ttu-id="3a18b-119">Jeder Typ, <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> implementiert</span><span class="sxs-lookup"><span data-stu-id="3a18b-119">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="3a18b-120">Beim Hinzufügen komplexen Inhalts können an diese Methode verschiedene Typen übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="3a18b-120">When adding complex content, various types can be passed to this method:</span></span>  
  
-   <span data-ttu-id="3a18b-121"><xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="3a18b-121"><xref:System.Xml.Linq.XObject></span></span>  
  
-   <span data-ttu-id="3a18b-122"><xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="3a18b-122"><xref:System.Xml.Linq.XNode></span></span>  
  
-   <span data-ttu-id="3a18b-123"><xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="3a18b-123"><xref:System.Xml.Linq.XAttribute></span></span>  
  
-   <span data-ttu-id="3a18b-124">Jeder Typ, implementiert<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="3a18b-124">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="3a18b-125">Wenn ein Objekt implementiert <xref:System.Collections.Generic.IEnumerable%601>, die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung hinzugefügt werden.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="3a18b-125">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="3a18b-126">Wenn die Auflistung enthält <xref:System.Xml.Linq.XNode>oder <xref:System.Xml.Linq.XAttribute>Objekte, die jedes Element in der Auflistung getrennt hinzugefügt.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="3a18b-126">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="3a18b-127">Wenn die Auflistung Text (oder Objekte, die in Text umgewandelt wurden) enthält, wird der Text in der Auflistung verkettet und als einzelner Textknoten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3a18b-127">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="3a18b-128">Wenn der Inhalt `null` ist, wird nichts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3a18b-128">If content is `null`, nothing is added.</span></span> <span data-ttu-id="3a18b-129">Bei der Übergabe einer Auflistung können Elemente der Auflistung `null` sein.</span><span class="sxs-lookup"><span data-stu-id="3a18b-129">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="3a18b-130">Ein `null`-Element in der Auflistung hat keine Auswirkungen auf die Struktur.</span><span class="sxs-lookup"><span data-stu-id="3a18b-130">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="3a18b-131">Ein hinzugefügtes Attribut muss innerhalb des Elements, in dem es enthalten ist, einen eindeutigen Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="3a18b-131">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="3a18b-132">Beim Hinzufügen von <xref:System.Xml.Linq.XNode>oder <xref:System.Xml.Linq.XAttribute>-Objekten der neue Inhalt kein übergeordnetes Element besitzt, klicken Sie dann die Objekte werden einfach angefügt der XML-Struktur.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="3a18b-132">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="3a18b-133">Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird der neue Inhalt geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="3a18b-133">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="3a18b-134">Gültiger Inhalt für Dokumente</span><span class="sxs-lookup"><span data-stu-id="3a18b-134">Valid Content for Documents</span></span>  
 <span data-ttu-id="3a18b-135">Es ist nicht möglich, einem Dokument Attribute und einfachen Inhalt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a18b-135">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="3a18b-136">Es gibt nicht viele Szenarios, die Sie erstellen eine <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> erfordern</span><span class="sxs-lookup"><span data-stu-id="3a18b-136">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="3a18b-137">Sie können in der Regel erstellen Sie stattdessen die XML-Strukturen mit einem <xref:System.Xml.Linq.XElement>Stammknoten.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3a18b-137">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="3a18b-138">Es sei denn, Sie haben eine bestimmte Anforderung zum Erstellen eines Dokuments (z. B., weil Sie verarbeitungsanweisungen und Kommentare auf der obersten Ebene zu erstellen, oder Sie Dokumenttypen unterstützen müssen), ist es oft hilfreich, <xref:System.Xml.Linq.XElement>als Stammknoten.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3a18b-138">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="3a18b-139">Als gültiger Inhalt für Dokumente gilt z. B.:</span><span class="sxs-lookup"><span data-stu-id="3a18b-139">Valid content for a document includes the following:</span></span>  
  
-   <span data-ttu-id="3a18b-140">NULL oder eins <xref:System.Xml.Linq.XDocumentType>Objekte.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="3a18b-140">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="3a18b-141">Die Dokumenttypen müssen vor dem Element kommen.</span><span class="sxs-lookup"><span data-stu-id="3a18b-141">The document types must come before the element.</span></span>  
  
-   <span data-ttu-id="3a18b-142">kein oder ein Element</span><span class="sxs-lookup"><span data-stu-id="3a18b-142">Zero or one element.</span></span>  
  
-   <span data-ttu-id="3a18b-143">keine oder mehrere Kommentare</span><span class="sxs-lookup"><span data-stu-id="3a18b-143">Zero or more comments.</span></span>  
  
-   <span data-ttu-id="3a18b-144">keine oder mehrere Verarbeitungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="3a18b-144">Zero or more processing instructions.</span></span>  
  
-   <span data-ttu-id="3a18b-145">keine oder mehrere Textknoten, die nur Leerraum enthalten</span><span class="sxs-lookup"><span data-stu-id="3a18b-145">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="3a18b-146">Konstruktoren und Funktionen, die das Hinzufügen von Inhalt erlauben</span><span class="sxs-lookup"><span data-stu-id="3a18b-146">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="3a18b-147">Die folgenden Methoden können Sie das untergeordnete Element ein <xref:System.Xml.Linq.XElement>oder ein <xref:System.Xml.Linq.XDocument>:</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3a18b-147">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="3a18b-148">Methode</span><span class="sxs-lookup"><span data-stu-id="3a18b-148">Method</span></span>|<span data-ttu-id="3a18b-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a18b-149">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3a18b-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></span></span>|<span data-ttu-id="3a18b-151">Erstellt eine <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3a18b-151">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="3a18b-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></span></span>|<span data-ttu-id="3a18b-153">Erstellt eine <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="3a18b-153">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="3a18b-154"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-154"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="3a18b-155">Fügt am Ende des untergeordneten Inhalts des <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> hinzu</span><span class="sxs-lookup"><span data-stu-id="3a18b-155">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="3a18b-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="3a18b-157">Fügt Inhalt nach dem <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="3a18b-157">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="3a18b-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="3a18b-159">Fügt Inhalt vor dem <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="3a18b-159">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="3a18b-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="3a18b-161">Fügt Inhalt am Anfang des untergeordneten Inhalts des <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="3a18b-161">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="3a18b-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></span></span>|<span data-ttu-id="3a18b-163">Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eine <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3a18b-163">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="3a18b-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span></span>|<span data-ttu-id="3a18b-165">Ersetzt die Attribute einer <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3a18b-165">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="3a18b-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span></span>|<span data-ttu-id="3a18b-167">Ersetzt die untergeordneten Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="3a18b-167">Replaces the children nodes with new content.</span></span>|  
|<span data-ttu-id="3a18b-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A></span><span class="sxs-lookup"><span data-stu-id="3a18b-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></span></span>|<span data-ttu-id="3a18b-169">Ersetzt einen Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="3a18b-169">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a18b-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a18b-170">See Also</span></span>  
 [<span data-ttu-id="3a18b-171">Erstellen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a18b-171">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
