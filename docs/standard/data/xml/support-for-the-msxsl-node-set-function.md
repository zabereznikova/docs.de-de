---
title: Unterstützung der msxsl:node-set()-Funktion
ms.date: 03/30/2017
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 26ae3014af93377dc106b5638ba194bd38e3dc9e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818543"
---
# <a name="support-for-the-msxslnode-set-function"></a>Unterstützung der msxsl:node-set()-Funktion
Mit der `msxsl:node-set`-Funktion können Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren. Die resultierende Knotengruppe enthält immer einen einzelnen Knoten und stellt den Stammknoten der Struktur dar.  
  
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).  
  
 Mit der `msxsl:node-set`-Funktion können Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren. Die resultierende Knotengruppe enthält immer einen einzelnen Knoten und stellt den Stammknoten der Struktur dar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel handelt es sich bei `$books` um eine Variable, die im Stylesheet eine Knotenstruktur darstellt. Die for-each`node-set`-Anweisung in Verbindung mit der -Funktion ermöglicht dem Benutzer, diese Knotenstruktur wie eine Knotengruppe zu durchlaufen.  
  
## <a name="nodesetxsl"></a>nodeset.xsl  
  
```xml  
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
                <author><xsl:value-of select="@author"/></author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a>Output  
 Die Ausgabe der Transformation lautet:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
