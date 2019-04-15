---
title: Unterstützung der msxsl:node-set()-Funktion
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a37220816ab320340b2dd5c048cc4ff2ad9724a3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330232"
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="0520f-102">Unterstützung der msxsl:node-set()-Funktion</span><span class="sxs-lookup"><span data-stu-id="0520f-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="0520f-103">Mit der `msxsl:node-set`-Funktion können Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0520f-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="0520f-104">Die resultierende Knotengruppe enthält immer einen einzelnen Knoten und stellt den Stammknoten der Struktur dar.</span><span class="sxs-lookup"><span data-stu-id="0520f-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0520f-105">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="0520f-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="0520f-106">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="0520f-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="0520f-107">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="0520f-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="0520f-108">Mit der `msxsl:node-set`-Funktion können Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0520f-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="0520f-109">Die resultierende Knotengruppe enthält immer einen einzelnen Knoten und stellt den Stammknoten der Struktur dar.</span><span class="sxs-lookup"><span data-stu-id="0520f-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0520f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0520f-110">Example</span></span>  
 <span data-ttu-id="0520f-111">Im folgenden Beispiel handelt es sich bei `$var` um eine Variable, die im Stylesheet eine Knotenstruktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="0520f-111">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="0520f-112">Die for-each`node-set`-Anweisung in Verbindung mit der -Funktion ermöglicht dem Benutzer, diese Knotenstruktur wie eine Knotengruppe zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0520f-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="0520f-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="0520f-113">nodeset.xsl</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="0520f-114">Output</span><span class="sxs-lookup"><span data-stu-id="0520f-114">Output</span></span>  
 <span data-ttu-id="0520f-115">Die Ausgabe der Transformation lautet:</span><span class="sxs-lookup"><span data-stu-id="0520f-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0520f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0520f-116">See also</span></span>

- [<span data-ttu-id="0520f-117">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="0520f-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
