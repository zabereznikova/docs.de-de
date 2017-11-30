---
title: "Knotensätze in Transformationen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4d6d2f5a68ce5cef9937edc136e52efcd5366df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="node-sets-in-transformations"></a>Knotensätze in Transformationen
Knotengruppen stellen einen von vier Grunddatentypen dar, die von XPath-Ausdrücken (XML Path) zurückgegeben werden. Eine Knotengruppe ist eine unsortierte Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde. Eine Knotengruppe kann einer Variablen in einem Stylesheet zugeordnet werden.  
  
> [!NOTE]
>  Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Finden Sie unter [mithilfe der Klasse "XslCompiledTransform"](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) für Weitere Informationen.  
  
 Knotengruppen stellen einen von vier Grunddatentypen dar, die von XPath-Ausdrücken zurückgegeben werden. Eine Knotengruppe ist eine unsortierte Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde. Eine Knotengruppe kann einer Variablen in einem Stylesheet zugeordnet werden. Diese Knotengruppe resultiert aus einem XPath-Ausdruck, der in einer Transformation in einem `select`-Attribut verwendet wird. Dabei entspricht das Verhalten dem einer Knotengruppe im Dokumentobjektmodell (DOM). Sie können mit der einen Satz von Methoden gezeigt eine Knotengruppe navigieren [Node Set Navigation mithilfe von XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), im Gegensatz zu einer Ergebnisstrukturfragment oder ein Ergebnisstrukturfragment in verwendet die <xref:System.Xml.XPath.XPathNodeIterator> für die Navigation.  
  
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
  
## <a name="output"></a>Ausgabe  
  
```  
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
 <xref:System.Xml.XPath.XPathNodeIterator>  
 [XSLT-Transformationen mit der XslTransform-Klasse](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [XslTransform-Klasse implementiert die XSLT-Prozessor](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
