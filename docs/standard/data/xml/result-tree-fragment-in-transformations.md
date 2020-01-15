---
title: Ergebnisstrukturfragment in Transformationen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
ms.openlocfilehash: 33d66b0a835be8bacab76ef9295ce8158385d8d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710257"
---
# <a name="result-tree-fragment-in-transformations"></a><span data-ttu-id="9e5e0-102">Ergebnisstrukturfragment in Transformationen</span><span class="sxs-lookup"><span data-stu-id="9e5e0-102">Result Tree Fragment in Transformations</span></span>

> [!NOTE]
> <span data-ttu-id="9e5e0-103">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="9e5e0-104">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="9e5e0-105">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="9e5e0-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

 <span data-ttu-id="9e5e0-106">Ergebnisstrukturfragmente sind lediglich spezielle Knotengruppentypen.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-106">Result tree fragments, also known as result tree fragments, are nothing more than a special type of node set.</span></span> <span data-ttu-id="9e5e0-107">Für sie können dieselben Funktionen ausgeführt werden wie für Knotengruppen.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-107">You can perform any function on them that can be performed on a node set.</span></span> <span data-ttu-id="9e5e0-108">Außerdem können Ergebnisstrukturfragmente mit der `node-set()`-Funktion in Knotengruppen konvertiert und anschließend überall verwendet werden, wo eine Knotengruppe verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-108">Or, you can also convert a result tree fragment to a node set using the `node-set()` function and subsequently use it any place that a node set can be used.</span></span>

 <span data-ttu-id="9e5e0-109">Ein Ergebnisstrukturfragment wird erstellt, wenn ein `<xsl:variable>`-Element oder ein `<xsl:param>`-Element in einem Stylesheet auf eine bestimmte Art und Weise verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-109">A result tree fragment is created as a result of using an `<xsl:variable>` or `<xsl:param>` element in a specific manner in a style sheet.</span></span> <span data-ttu-id="9e5e0-110">Im Folgenden wird die Syntax für das `variable`-Element und das `parameter`-Element dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9e5e0-110">The syntax for the `variable` and `parameter` elements is as follows:</span></span>

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

<span data-ttu-id="9e5e0-111">Beim `parameter`-Element kann der Wert dem `Qname` (qualifizierter Name) auf verschiedene Weise zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-111">For the `parameter` element, the value is assigned to the qualified name (`Qname`) in several ways.</span></span> <span data-ttu-id="9e5e0-112">Sie können dem Parameter einen Standardwert zuweisen, indem Inhalt aus dem XPath-Ausdruck im `select`-Attribut zurückgegeben wird, oder indem dem Parameter der Inhalt des Vorlagenkörpers zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-112">You can assign a default value to the parameter by returning content from the XML Path Language (XPath) expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="9e5e0-113">Dem `variable`-Element kann der Wert ebenfalls auf verschiedene Weise zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-113">For the `variable` element, the value is also assigned in several ways.</span></span> <span data-ttu-id="9e5e0-114">Die Zuordnung kann erfolgen, indem der Inhalt aus dem XPath-Ausdruck im `select`-Attribut zurückgegeben wird, oder indem der Inhalt des Vorlagenkörpers zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-114">You can assign it by returning content from the XPath expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="9e5e0-115">Wenn bei einem `parameter`-Element und einem `variable`-Element der Wert durch den XPath-Ausdruck zugeordnet wird, wird einer der vier XPath-Grundtypen zurückgegeben: Boolean (boolescher Wert), string (Zeichenfolge), number (Zahl) oder node set (Knotengruppe).</span><span class="sxs-lookup"><span data-stu-id="9e5e0-115">For both the `parameter` and `variable` elements, if a value is assigned by the XPath expression, then one of the four basic XPath types will be returned: Boolean, string, number, or node set.</span></span> <span data-ttu-id="9e5e0-116">Wenn der Wert aus einem Vorlagenkörper mit Inhalt stammt, wird kein XPath-Datentyp zurückgegeben, sondern ein Ergebnisstrukturfragment.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-116">When the value is given by using a non-empty template body, then a non-XPath data type is returned, and that will be a result tree fragment.</span></span>

<span data-ttu-id="9e5e0-117">Nur wenn eine Variable nicht an einen der vier XPath-Grunddatentypen, sondern an ein Ergebnisstrukturfragment gebunden ist, gibt eine XPath-Abfrage einen Typ zurück, der nicht zu den vier XPath-Objekttypen gehört.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-117">When a variable is bound to a result tree fragment instead of one of the four basic XPath data types, this is the only time that an XPath query returns a type that is not one of the four XPath object types.</span></span> <span data-ttu-id="9e5e0-118">Das Verhalten von Ergebnisstrukturfragmenten wird in der [W3C-Spezifikation](https://www.w3.org/TR/xslt-10/), [Abschnitt 11.1, „Result Tree Fragments“](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments), bis [Abschnitt 11.6, „Passing Parameters to Templates“](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates), erörtert.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-118">Result tree fragments and their behavior are discussed in the [World Wide Web Consortium (W3C) specification](https://www.w3.org/TR/xslt-10/), [section 11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) through [section 11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates).</span></span> <span data-ttu-id="9e5e0-119">Darüber hinaus werden in [Abschnitt 1, „Introduction“](https://www.w3.org/TR/xslt-10/#section-Introduction) Möglichkeiten erläutert, wie Vorlagen auch Elemente aus dem XSLT-Namespace enthalten können, die Ergebnisstrukturfragmente zurückgeben oder erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-119">Also, [section 1 Introduction](https://www.w3.org/TR/xslt-10/#section-Introduction) discusses how templates can contain elements from the XSLT namespace that return or create result tree fragments.</span></span>

<span data-ttu-id="9e5e0-120">Ein Ergebnisstrukturfragment verhält sich im Grunde wie eine Knotengruppe mit lediglich einem einzelnen Stammknoten.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-120">A result tree fragment, in concept, behaves like a node set with nothing more than a single root node.</span></span> <span data-ttu-id="9e5e0-121">Die übrigen zurückgegebenen Knoten sind jedoch untergeordnete Knoten.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-121">However, the rest of the nodes returned are child nodes.</span></span> <span data-ttu-id="9e5e0-122">Zur programmgesteuerten Anzeige der untergeordneten Knoten kopieren Sie das Ergebnisstrukturfragment mithilfe des `<xsl:copy-of>`-Elements in die Ergebnisstruktur.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-122">To programmatically see the child nodes, copy the result tree fragment to the result tree using the `<xsl:copy-of>` element.</span></span> <span data-ttu-id="9e5e0-123">Beim Ausführen des copy-of-Vorgangs werden auch alle untergeordneten Knoten der Reihe nach in die Ergebnisstruktur kopiert.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-123">When the copy-of is performed, all the child nodes are also copied to the result tree in sequence.</span></span> <span data-ttu-id="9e5e0-124">Erst wenn `copy` oder `copy-of` verwendet wird, ist ein Ergebnisstrukturfragment Teil der Ergebnisstruktur oder der Transformationsausgabe.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-124">Until a `copy` or `copy-of` is used, a result tree fragment is not part of the result tree or the output from the transformation.</span></span>

<span data-ttu-id="9e5e0-125">Zum Durchlaufen der zurückgegebenen Knoten eines Ergebnisstrukturfragments wird ein <xref:System.Xml.XPath.XPathNavigator> verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-125">To iterate over the returned nodes of a result tree fragment, an <xref:System.Xml.XPath.XPathNavigator> is used.</span></span> <span data-ttu-id="9e5e0-126">Im folgenden Codebeispiel wird dargestellt, wie ein Ergebnisstrukturfragment in einem Stylesheet erstellt wird. Dabei wird die Funktion mit einem Parameter `fragment` aufgerufen, der XML enthält.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-126">The following code sample shows how to create a result tree fragment within a style sheet by calling the function with a parameter `fragment`, which contains XML.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:var name="fragment">
        <node1>
            <node2/>
        </node1>
    <xsl:var>

  <msxsl:script language="C#" implements-prefix="user">
    function NodeFragment(XPathNavigator nav)
    {
      if (nav.HasSelection == false)
        XPathNavigator.MoveToNext();
      return;
    }
  </msxsl:script>

    <xsl:template match="/">
            <xsl:value-of select="user:NodeFragment(msxml:node-set($fragment))"/>
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="9e5e0-127">Im nächsten Beispiel wird eine Variable im RTF-Format (Rich Text Format) und damit ein Typ eines Ergebnisstrukturfragments dargestellt, der nicht in eine Knotengruppe konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-127">Here is another sample showing a variable, which is in Rich Text Format (RTF), and hence, a type of result tree fragment, that is not converted to a node set.</span></span> <span data-ttu-id="9e5e0-128">Stattdessen erfolgt eine Übergabe an eine Skriptfunktion, und <xref:System.Xml.XPath.XPathNavigator> wird zum Navigieren durch die Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-128">Instead, it is passed to a script function, and the <xref:System.Xml.XPath.XPathNavigator> is used to navigate over the nodes.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNavigator nav)
    {
        bool b = nav.MoveToFirstChild();
        if (b)
            return nav.Value;
        else
            return "Does not exist";
    }

]]>

</msxsl:script>

<xsl:template match="/">
    <first_book>
        <xsl:value-of select="user:func($node-fragment)"/>
    </first_book>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="9e5e0-129">In der folgenden Ausgabe wird das Ergebnis der XML-Transformation mit diesem Stylesheet dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-129">The result of transforming any XML with this style sheet is shown in the following output.</span></span>

## <a name="output"></a><span data-ttu-id="9e5e0-130">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="9e5e0-130">Output</span></span>

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

<span data-ttu-id="9e5e0-131">Wie oben angegeben, können Sie mit der `node-set`-Funktion ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-131">As stated above, the `node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="9e5e0-132">Der resultierende Knoten enthält immer einen einzelnen Knoten, der den Stammknoten der Struktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-132">The resulting node always contains a single node that is the root node of the tree.</span></span> <span data-ttu-id="9e5e0-133">Wenn Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren, können Sie es überall verwenden, wo reguläre Knotengruppen verwendet werden, z. B. in einer `select` for-each-Anweisung oder im Wert eines -Attributs.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-133">If you convert a result tree fragment to a node set, then you can use it anywhere a regular node set is used, such as in a for-each statement or in the value of a `select` attribute.</span></span> <span data-ttu-id="9e5e0-134">Im folgenden Beispiel wird die Umwandlung eines Fragments in eine Knotengruppe und die anschließende Verwendung als Knotengruppe dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9e5e0-134">The following lines of code show the fragment being converted to a node set and used as a node set:</span></span>

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

<span data-ttu-id="9e5e0-135">Wenn Sie ein Fragment in eine Knotengruppe konvertieren, wird <xref:System.Xml.XPath.XPathNavigator> nicht mehr zum Navigieren durch die Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-135">When a fragment is converted to a node set, you no longer use the <xref:System.Xml.XPath.XPathNavigator> to navigate over it.</span></span> <span data-ttu-id="9e5e0-136">Stattdessen verwenden Sie für Knotengruppen <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-136">For a node set, you use the <xref:System.Xml.XPath.XPathNodeIterator> instead.</span></span>

<span data-ttu-id="9e5e0-137">Im folgenden Beispiel handelt es sich bei `$var` um eine Variable, die im Stylesheet eine Knotenstruktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-137">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="9e5e0-138">Die „for-each“-Anweisung in Verbindung mit der `node-set`-Funktion ermöglicht es Benutzern, diese Struktur wie eine Knotengruppe zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-138">The for-each statement, combined with the `node-set` function, allows the user to iterate over this tree as a node set.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:variable name="states">
        <node1>AL</node1>
        <node1>CA</node1>
        <node1>CO</node1>
        <node1>WA</node1>
    </xsl:variable>

    <xsl:template match="/">
            <xsl:for-each select="msxsl:node-set($states)"/> 
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="9e5e0-139">Im nächsten Beispiel wird eine RTF-Variable und damit ein Ergebnisstrukturfragmenttyp dargestellt, der in eine Knotengruppe konvertiert und anschließend als XPathNodeIterator an eine Skriptfunktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9e5e0-139">Here is another example of a variable that is in RTF, and hence of type result tree fragment, that is converted to a node set before being passed to a script function as XPathNodeIterator.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNodeIterator it)
    {
        it.MoveNext(); 
        return it.Current.Value; 
        //it.Current returns XPathNavigator positioned on the current node
    }

]]>

</msxsl:script>
<xsl:template match="/">
    <books>
        <xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>
    </books>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="9e5e0-140">Nachfolgend wird das Ergebnis der XML-Transformation mit diesem Stylesheet dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9e5e0-140">The following is the result of transforming XML with this style sheet:</span></span>

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a><span data-ttu-id="9e5e0-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e5e0-141">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="9e5e0-142">XSLT-Transformationen mit der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="9e5e0-142">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="9e5e0-143">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="9e5e0-143">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
