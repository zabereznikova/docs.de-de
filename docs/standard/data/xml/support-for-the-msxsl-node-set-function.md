---
title: "Unterst&#252;tzung der msxsl:node-set()-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Unterst&#252;tzung der msxsl:node-set()-Funktion
Mit der `msxsl:node-set`\-Funktion können Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren.  Die resultierende Knotengruppe enthält immer einen einzelnen Knoten und stellt den Stammknoten der Struktur dar.  
  
> [!NOTE]
>  Die <xref:System.Xml.Xsl.XslTransform>\-Klasse ist in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] veraltet.  Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>\-Klasse können Sie XSLT\-Transformationen \(Extensible Stylesheet Language for Transformations\) vornehmen.  Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform\-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform\-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Mit der `msxsl:node-set`\-Funktion können Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren.  Die resultierende Knotengruppe enthält immer einen einzelnen Knoten und stellt den Stammknoten der Struktur dar.  
  
## Beispiel  
 Im folgenden Beispiel handelt es sich bei `$var` um eine Variable, die im Stylesheet eine Knotenstruktur darstellt.  Die **for\-each**\-Anweisung in Verbindung mit der `node-set`\-Funktion ermöglicht dem Benutzer, diese Knotenstruktur wie eine Knotengruppe zu durchlaufen.  
  
## nodeset.xsl  
  
```  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">   
                <author><xsl:value-of select="@author"/)</author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## Ausgabe  
 Die Ausgabe der Transformation lautet:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## Siehe auch  
 [Implementierung des XSLT\-Prozessors durch die XslTransform\-Klasse](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)