---
title: Knotensätze in Transformationen
ms.date: 03/30/2017
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
ms.openlocfilehash: 2ace103d9721b2adecb08a25ab89cf9b0f05bb93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734113"
---
# <a name="node-sets-in-transformations"></a>Knotensätze in Transformationen

Knotengruppen stellen einen von vier Grunddatentypen dar, die von XPath-Ausdrücken (XML Path) zurückgegeben werden. Eine Knotengruppe ist eine unsortierte Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde. Eine Knotengruppe kann einer Variablen in einem Stylesheet zugeordnet werden.  
  
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).  
  
 Knotengruppen stellen einen von vier Grunddatentypen dar, die von XPath-Ausdrücken zurückgegeben werden. Eine Knotengruppe ist eine unsortierte Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde. Eine Knotengruppe kann einer Variablen in einem Stylesheet zugeordnet werden. Diese Knotengruppe resultiert aus einem XPath-Ausdruck, der in einer Transformation in einem `select`-Attribut verwendet wird. Dabei entspricht das Verhalten dem einer Knotengruppe im Dokumentobjektmodell (DOM). Anders als bei Ergebnisstrukturfragmenten oder Ergebnisstrukturfragmenten, bei denen <xref:System.Xml.XPath.XPathNodeIterator> zur Navigation verwendet wird, können Sie zur Navigation in einer Knotengruppe eine Reihe von Methoden verwenden. Diese werden unter [Navigieren in Knotengruppen mit XPathNavigator](node-set-navigation-using-xpathnavigator.md) dargestellt.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Knotengruppe durchlaufen wird, wenn ein `variable`-Element oder ein `parameter`-Element in einem Stylesheet eine Knotengruppe auswertet.  
  
## <a name="style-sheet"></a>Stylesheet  
  
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
  
## <a name="input"></a>Eingabe  
  
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
  
## <a name="output"></a>Output  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XPath.XPathNodeIterator>
- [XSLT-Transformationen mit der XslTransform-Klasse](xslt-transformations-with-the-xsltransform-class.md)
- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
