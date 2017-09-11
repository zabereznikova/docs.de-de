---
title: Erstellen von XML-Strukturen in C# (LINQ to XML)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ac95fcf49736b554c8a3d4d0061f63b3ac4d3f65
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a><span data-ttu-id="a8611-102">Erstellen von XML-Strukturen in C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a8611-102">Creating XML Trees in C# (LINQ to XML)</span></span>
<span data-ttu-id="a8611-103">Dieser Abschnitt enthält Informationen zum Erstellen von XML-Strukturen in C#.</span><span class="sxs-lookup"><span data-stu-id="a8611-103">This section provides information about creating XML trees in C#.</span></span>  
  
 <span data-ttu-id="a8611-104">Informationen zur Verwendung der Ergebnisse von LINQ-Abfragen als Inhalt für eine <xref:System.Xml.Linq.XElement>-Klasse finden Sie unter [Funktionale Konstruktion (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a8611-104">For information about using the results of LINQ queries as the content for an <xref:System.Xml.Linq.XElement>, see [Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="constructing-elements"></a><span data-ttu-id="a8611-105">Konstruieren von Elementen</span><span class="sxs-lookup"><span data-stu-id="a8611-105">Constructing Elements</span></span>  
 <span data-ttu-id="a8611-106">Die Signaturen der <xref:System.Xml.Linq.XElement>-Konstruktoren und der <xref:System.Xml.Linq.XAttribute>-Konstruktoren ermöglichen es Ihnen, den Inhalt des Elements oder Attributs als Argumente an den Konstruktor zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8611-106">The signatures of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors let you pass the contents of the element or attribute as arguments to the constructor.</span></span> <span data-ttu-id="a8611-107">Da einer der Konstruktoren eine variable Anzahl von Argumenten akzeptiert, können Sie jede beliebige Anzahl von untergeordneten Elementen übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8611-107">Because one of the constructors takes a variable number of arguments, you can pass any number of child elements.</span></span> <span data-ttu-id="a8611-108">Natürlich kann jedes dieser untergeordneten Elemente wiederum untergeordnete Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="a8611-108">Of course, each of those child elements can contain their own child elements.</span></span> <span data-ttu-id="a8611-109">Für jedes Element können Sie eine beliebige Anzahl von Attributen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a8611-109">For any element, you can add any number of attributes.</span></span>  
  
 <span data-ttu-id="a8611-110">Wenn beim Hinzufügen von <xref:System.Xml.Linq.XNode>-Objekten (einschließlich <xref:System.Xml.Linq.XElement>) oder von <xref:System.Xml.Linq.XAttribute>-Objekten der neue Inhalt kein übergeordnetes Element besitzt, werden die Objekte einfach an die XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-110">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="a8611-111">Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-111">If the new content already is parented, and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span> <span data-ttu-id="a8611-112">Dies wird im letzten Beispiel in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8611-112">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="a8611-113">Zum Erstellen eines `contacts`-<xref:System.Xml.Linq.XElement>-Objekts können Sie den folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="a8611-113">To create a `contacts`<xref:System.Xml.Linq.XElement>, you could use the following code:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="a8611-114">Bei ordnungsgemäßen Einzügen ähnelt der zum Konstruieren von <xref:System.Xml.Linq.XElement>-Objekten verwendete Code sehr stark der Struktur des zugrunde liegenden XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="a8611-114">If indented properly, the code to construct <xref:System.Xml.Linq.XElement> objects closely resembles the structure of the underlying XML.</span></span>  
  
## <a name="xelement-constructors"></a><span data-ttu-id="a8611-115">"XElement"-Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="a8611-115">XElement Constructors</span></span>  
 <span data-ttu-id="a8611-116">Die <xref:System.Xml.Linq.XElement>-Klasse verwendet für die funktionale Konstruktion die folgenden Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="a8611-116">The <xref:System.Xml.Linq.XElement> class uses the following constructors for functional construction.</span></span> <span data-ttu-id="a8611-117">Beachten Sie, dass es auch noch andere Konstruktoren für <xref:System.Xml.Linq.XElement> gibt. Diese werden nicht für die funktionale Konstruktion verwendet und sind daher hier auch nicht aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a8611-117">Note that there are some other constructors for <xref:System.Xml.Linq.XElement>, but because they are not used for functional construction they are not listed here.</span></span>  
  
|<span data-ttu-id="a8611-118">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="a8611-118">Constructor</span></span>|<span data-ttu-id="a8611-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8611-119">Description</span></span>|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|<span data-ttu-id="a8611-120">Erstellt ein <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a8611-120">Creates an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="a8611-121">Der `name`-Parameter gibt den Namen des Elements an, und `content` gibt den Inhalt des Elements an.</span><span class="sxs-lookup"><span data-stu-id="a8611-121">The `name` parameter specifies the name of the element; `content` specifies the content of the element.</span></span>|  
|`XElement(XName name)`|<span data-ttu-id="a8611-122">Erstellt ein <xref:System.Xml.Linq.XElement> mit seinem <xref:System.Xml.Linq.XName>, initialisiert für den angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="a8611-122">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span>|  
|`XElement(XName name, params object[] content)`|<span data-ttu-id="a8611-123">Erstellt ein <xref:System.Xml.Linq.XElement> mit seinem <xref:System.Xml.Linq.XName>, initialisiert für den angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="a8611-123">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span> <span data-ttu-id="a8611-124">Die Attribute und/oder untergeordneten Elemente werden aus dem Inhalt der Parameterliste erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8611-124">The attributes and/or child elements are created from the contents of the parameter list.</span></span>|  
  
 <span data-ttu-id="a8611-125">Der `content`-Parameter ist äußerst flexibel.</span><span class="sxs-lookup"><span data-stu-id="a8611-125">The `content` parameter is extremely flexible.</span></span> <span data-ttu-id="a8611-126">Er unterstützt jede Art von Objekt, das ein gültiges untergeordnetes Element eines <xref:System.Xml.Linq.XElement> ist.</span><span class="sxs-lookup"><span data-stu-id="a8611-126">It supports any type of object that is a valid child of an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="a8611-127">Die folgenden Regeln gelten für andere Arten von Objekten, die in diesem Parameter übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="a8611-127">The following rules apply to different types of objects passed in this parameter:</span></span>  
  
-   <span data-ttu-id="a8611-128">Eine Zeichenfolge wird als Textinhalt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-128">A string is added as text content.</span></span>  
  
-   <span data-ttu-id="a8611-129">Ein <xref:System.Xml.Linq.XElement> wird als untergeordnetes Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-129">An <xref:System.Xml.Linq.XElement> is added as a child element.</span></span>  
  
-   <span data-ttu-id="a8611-130">Ein <xref:System.Xml.Linq.XAttribute> wird als Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-130">An <xref:System.Xml.Linq.XAttribute> is added as an attribute.</span></span>  
  
-   <span data-ttu-id="a8611-131">Eine <xref:System.Xml.Linq.XProcessingInstruction>, ein <xref:System.Xml.Linq.XComment> oder ein <xref:System.Xml.Linq.XText> wird als untergeordneter Inhalt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-131">An <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, or <xref:System.Xml.Linq.XText> is added as child content.</span></span>  
  
-   <span data-ttu-id="a8611-132">Eine <xref:System.Collections.IEnumerable> wird aufgelistet, und diese Regeln werden rekursiv auf die Ergebnisse angewendet.</span><span class="sxs-lookup"><span data-stu-id="a8611-132">An <xref:System.Collections.IEnumerable> is enumerated, and these rules are applied recursively to the results.</span></span>  
  
-   <span data-ttu-id="a8611-133">Für alle anderen Arten wird deren `ToString`-Methode aufgerufen, und das Ergebnis wird als Textinhalt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-133">For any other type, its `ToString` method is called and the result is added as text content.</span></span>  
  
### <a name="creating-an-xelement-with-content"></a><span data-ttu-id="a8611-134">Erstellen eines "XElement" mit Inhalt</span><span class="sxs-lookup"><span data-stu-id="a8611-134">Creating an XElement with Content</span></span>  
 <span data-ttu-id="a8611-135">Sie können mit einem einzigen Methodenaufruf ein <xref:System.Xml.Linq.XElement> erstellen, das einfachen Inhalt enthält.</span><span class="sxs-lookup"><span data-stu-id="a8611-135">You can create an <xref:System.Xml.Linq.XElement> that contains simple content with a single method call.</span></span> <span data-ttu-id="a8611-136">Geben Sie dazu den Inhalt wie folgt als zweiten Parameter an:</span><span class="sxs-lookup"><span data-stu-id="a8611-136">To do this, specify the content as the second parameter, as follows:</span></span>  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="a8611-137">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8611-137">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 <span data-ttu-id="a8611-138">Sie können jede Art von Objekt als Inhalt übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8611-138">You can pass any type of object as the content.</span></span> <span data-ttu-id="a8611-139">So erstellt z. B. der folgende Code ein Element, das eine Gleitkommazahl als Inhalt enthält:</span><span class="sxs-lookup"><span data-stu-id="a8611-139">For example, the following code creates an element that contains a floating point number as content:</span></span>  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="a8611-140">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8611-140">This example produces the following output:</span></span>  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 <span data-ttu-id="a8611-141">Die Gleitkommazahl wird geschachtelt und an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8611-141">The floating point number is boxed and passed in to the constructor.</span></span> <span data-ttu-id="a8611-142">Die geschachtelte Zahl wird in eine Zeichenfolge konvertiert und als Inhalt des Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8611-142">The boxed number is converted to a string and used as the content of the element.</span></span>  
  
### <a name="creating-an-xelement-with-a-child-element"></a><span data-ttu-id="a8611-143">Erstellen eines "XElement" mit einem untergeordneten Element</span><span class="sxs-lookup"><span data-stu-id="a8611-143">Creating an XElement with a Child Element</span></span>  
 <span data-ttu-id="a8611-144">Wenn Sie eine Instanz der <xref:System.Xml.Linq.XElement>-Klasse für das Inhaltsargument übergeben, erstellt der Konstruktor ein Element mit einem untergeordneten Element:</span><span class="sxs-lookup"><span data-stu-id="a8611-144">If you pass an instance of the <xref:System.Xml.Linq.XElement> class for the content argument, the constructor creates an element with a child element:</span></span>  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 <span data-ttu-id="a8611-145">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8611-145">This example produces the following output:</span></span>  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a><span data-ttu-id="a8611-146">Erstellen eines "XElement" mit mehreren untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="a8611-146">Creating an XElement with Multiple Child Elements</span></span>  
 <span data-ttu-id="a8611-147">Sie können für den Inhalt mehrere <xref:System.Xml.Linq.XElement>-Objekte übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8611-147">You can pass in a number of <xref:System.Xml.Linq.XElement> objects for the content.</span></span> <span data-ttu-id="a8611-148">Jedes dieser <xref:System.Xml.Linq.XElement>-Objekte wird zu einem untergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="a8611-148">Each of the <xref:System.Xml.Linq.XElement> objects is included as a child element.</span></span>  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 <span data-ttu-id="a8611-149">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8611-149">This example produces the following output:</span></span>  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 <span data-ttu-id="a8611-150">Sie können eine ganze XML-Struktur erstellen, indem Sie das oben erwähnte Beispiel wie folgt erweitern:</span><span class="sxs-lookup"><span data-stu-id="a8611-150">By extending the above example, you can create an entire XML tree, as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),                                                   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 <span data-ttu-id="a8611-151">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8611-151">This example produces the following output:</span></span>  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="a8611-152">Erstellen eines leeren Elements</span><span class="sxs-lookup"><span data-stu-id="a8611-152">Creating an Empty Element</span></span>  
 <span data-ttu-id="a8611-153">Wenn Sie ein leeres <xref:System.Xml.Linq.XElement> erstellen möchten, übergeben Sie einfach keinen Inhalt an den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a8611-153">To create an empty <xref:System.Xml.Linq.XElement>, you do not pass any content to the constructor.</span></span> <span data-ttu-id="a8611-154">Das folgende Beispiel erstellt ein leeres Element:</span><span class="sxs-lookup"><span data-stu-id="a8611-154">The following example creates an empty element:</span></span>  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="a8611-155">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8611-155">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a><span data-ttu-id="a8611-156">Anfügen oder Klonen?</span><span class="sxs-lookup"><span data-stu-id="a8611-156">Attaching vs. Cloning</span></span>  
 <span data-ttu-id="a8611-157">Wie bereits erwähnt, werden beim Hinzufügen von <xref:System.Xml.Linq.XNode>-Objekten (einschließlich <xref:System.Xml.Linq.XElement>) oder von <xref:System.Xml.Linq.XAttribute>-Objekten für den Fall, dass der neue Inhalt kein übergeordnetes Element besitzt, die Objekte einfach an die XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-157">As mentioned previously, when adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="a8611-158">Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="a8611-158">If the new content already is parented and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  
```  
  
 <span data-ttu-id="a8611-159">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8611-159">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8611-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8611-160">See Also</span></span>  
 [<span data-ttu-id="a8611-161">Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))</span><span class="sxs-lookup"><span data-stu-id="a8611-161">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)

