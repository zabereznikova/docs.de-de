---
title: Knotensätze in Transformationen
ms.date: 03/30/2017
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
ms.openlocfilehash: 72b3af5b471d73cc159dd700ddd29c4ffb5ea639
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830115"
---
# <a name="node-sets-in-transformations"></a><span data-ttu-id="a3585-102">Knotensätze in Transformationen</span><span class="sxs-lookup"><span data-stu-id="a3585-102">Node Sets in Transformations</span></span>
<span data-ttu-id="a3585-103">Knotengruppen stellen einen von vier Grunddatentypen dar, die von XPath-Ausdrücken (XML Path) zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3585-103">Node sets are one of four basic data types that are returned from XML Path Language (XPath) expressions.</span></span> <span data-ttu-id="a3585-104">Eine Knotengruppe ist eine unsortierte Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde. Eine Knotengruppe kann einer Variablen in einem Stylesheet zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a3585-104">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3585-105">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a3585-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="a3585-106">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a3585-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="a3585-107">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="a3585-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="a3585-108">Knotengruppen stellen einen von vier Grunddatentypen dar, die von XPath-Ausdrücken zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3585-108">Node sets are one of four basic data types that are returned from XPath expressions.</span></span> <span data-ttu-id="a3585-109">Eine Knotengruppe ist eine unsortierte Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde. Eine Knotengruppe kann einer Variablen in einem Stylesheet zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a3585-109">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span> <span data-ttu-id="a3585-110">Diese Knotengruppe resultiert aus einem XPath-Ausdruck, der in einer Transformation in einem `select`-Attribut verwendet wird. Dabei entspricht das Verhalten dem einer Knotengruppe im Dokumentobjektmodell (DOM).</span><span class="sxs-lookup"><span data-stu-id="a3585-110">This node set, which is a result of an XPath expression used in a `select` attribute in a transformation, has the same behavior as a node set from the XML Document Object Model (DOM).</span></span> <span data-ttu-id="a3585-111">Anders als bei Ergebnisstrukturfragmenten oder Ergebnisstrukturfragmenten, bei denen <xref:System.Xml.XPath.XPathNodeIterator> zur Navigation verwendet wird, können Sie zur Navigation in einer Knotengruppe eine Reihe von Methoden verwenden. Diese werden unter [Navigieren in Knotengruppen mit XPathNavigator](node-set-navigation-using-xpathnavigator.md) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a3585-111">You can navigate a node set using a set of methods shown in [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md), unlike a result tree fragment or result tree fragment, which uses the <xref:System.Xml.XPath.XPathNodeIterator> for navigation.</span></span>  
  
 <span data-ttu-id="a3585-112">Im folgenden Codebeispiel wird veranschaulicht, wie eine Knotengruppe durchlaufen wird, wenn ein `variable`-Element oder ein `parameter`-Element in einem Stylesheet eine Knotengruppe auswertet.</span><span class="sxs-lookup"><span data-stu-id="a3585-112">The following code sample shows how to iterate over a node set when a `variable` or `parameter` element in a style sheet evaluates to a node set.</span></span>  
  
## <a name="style-sheet"></a><span data-ttu-id="a3585-113">Stylesheet</span><span class="sxs-lookup"><span data-stu-id="a3585-113">Style Sheet</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
    <xsl:variable name="x" select="bookstore/book/title"></xsl:variable>  
  
    <xsl:template match="/">  
        <xsl:for-each select="$x">  
            ******  
            <xsl:value-of select="."></xsl:value-of>  
            ******  
        </xsl:for-each>  
    </xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="input"></a><span data-ttu-id="a3585-114">Eingabe</span><span class="sxs-lookup"><span data-stu-id="a3585-114">Input</span></span>  
  
```xml  
<bookstore>  
   <book style="autobiography">  
      <title>Seven Years in Trenton</title>  
   </book>  
  
   <book style="autobiography">  
      <title>Seven Years in Trenton2</title>  
   </book>  
  
   <book style="textbook">  
      <title>History of Trenton Vol 3</title>  
   </book>  
</bookstore>  
```  
  
## <a name="output"></a><span data-ttu-id="a3585-115">Output</span><span class="sxs-lookup"><span data-stu-id="a3585-115">Output</span></span>  
  
```output  
******  
Seven Years in Trenton  
******  
  
******  
Seven Years in Trenton2  
******  
  
******  
History of Trenton Vol 3  
******  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3585-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3585-116">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="a3585-117">XSLT-Transformationen mit der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="a3585-117">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="a3585-118">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="a3585-118">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
