---
title: Beibehalten von Leerzeichen während Serializing2
ms.date: 07/20/2015
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
ms.openlocfilehash: a08d69a817c3e493e571d1b3b98f6f2a144ad995
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254515"
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="e7519-102">Beibehalten von Leerzeichen beim Serialisieren</span><span class="sxs-lookup"><span data-stu-id="e7519-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="e7519-103">In diesem Thema wird beschrieben, wie Sie das Leerraumverhalten beim Serialisieren von XML-Strukturen steuern können.</span><span class="sxs-lookup"><span data-stu-id="e7519-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="e7519-104">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7519-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="e7519-105">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="e7519-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="e7519-106">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7519-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="e7519-107">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="e7519-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="e7519-108">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e7519-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="e7519-109">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7519-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="e7519-110">Leerraumverhalten von Methoden, die XML-Strukturen serialisieren</span><span class="sxs-lookup"><span data-stu-id="e7519-110">White Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="e7519-111">Die folgenden Methoden in den Klassen <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument> serialisieren eine XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="e7519-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="e7519-112">Sie können XML-Strukturen in eine Datei, in einen <xref:System.IO.TextReader> oder in einen <xref:System.Xml.XmlReader> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="e7519-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="e7519-113">Die `ToString`-Methode nimmt eine Serialisierung in eine Zeichenfolge vor.</span><span class="sxs-lookup"><span data-stu-id="e7519-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="e7519-114">Wenn die Methode nicht <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, formatiert die Methode den serialisierten XML-Code, indem sie ihn mit Einzügen versieht.</span><span class="sxs-lookup"><span data-stu-id="e7519-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="e7519-115">In diesem Fall wird der gesamte nicht signifikante Leerraum in der XML-Struktur verworfen.</span><span class="sxs-lookup"><span data-stu-id="e7519-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="e7519-116">Wenn die Methode <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, können Sie angeben, dass der serialisierte XML-Code nicht formatiert (eingerückt) werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7519-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="e7519-117">In diesem Fall wird der gesamte Leerraum in der XML-Struktur beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e7519-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7519-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7519-118">See Also</span></span>  
 [<span data-ttu-id="e7519-119">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7519-119">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
