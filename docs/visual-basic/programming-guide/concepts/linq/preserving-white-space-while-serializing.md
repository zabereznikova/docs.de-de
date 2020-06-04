---
title: Beibehalten von Leerzeichen während Serializing2
ms.date: 07/20/2015
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
ms.openlocfilehash: e9b73089830bf7e6cb0ea9e469bf667f12c571d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396401"
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="bc94f-102">Beibehalten von Leerzeichen beim Serialisieren</span><span class="sxs-lookup"><span data-stu-id="bc94f-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="bc94f-103">In diesem Thema wird beschrieben, wie Sie das Leerraumverhalten beim Serialisieren von XML-Strukturen steuern können.</span><span class="sxs-lookup"><span data-stu-id="bc94f-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="bc94f-104">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bc94f-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="bc94f-105">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="bc94f-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="bc94f-106">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc94f-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="bc94f-107">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="bc94f-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="bc94f-108">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bc94f-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="bc94f-109">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bc94f-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="bc94f-110">Leerraumverhalten von Methoden, die XML-Strukturen serialisieren</span><span class="sxs-lookup"><span data-stu-id="bc94f-110">White Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="bc94f-111">Die folgenden Methoden in den Klassen <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument> serialisieren eine XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="bc94f-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="bc94f-112">Sie können XML-Strukturen in eine Datei, in einen <xref:System.IO.TextReader> oder in einen <xref:System.Xml.XmlReader> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="bc94f-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="bc94f-113">Die `ToString`-Methode nimmt eine Serialisierung in eine Zeichenfolge vor.</span><span class="sxs-lookup"><span data-stu-id="bc94f-113">The `ToString` method serializes to a string.</span></span>  
  
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
- [<span data-ttu-id="bc94f-114">XElement.ToString()</span><span class="sxs-lookup"><span data-stu-id="bc94f-114">XElement.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
- [<span data-ttu-id="bc94f-115">XDocument.ToString()</span><span class="sxs-lookup"><span data-stu-id="bc94f-115">XDocument.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
 <span data-ttu-id="bc94f-116">Wenn die Methode nicht <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, formatiert die Methode den serialisierten XML-Code, indem sie ihn mit Einzügen versieht.</span><span class="sxs-lookup"><span data-stu-id="bc94f-116">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="bc94f-117">In diesem Fall wird der gesamte nicht signifikante Leerraum in der XML-Struktur verworfen.</span><span class="sxs-lookup"><span data-stu-id="bc94f-117">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="bc94f-118">Wenn die Methode <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, können Sie angeben, dass der serialisierte XML-Code nicht formatiert (eingerückt) werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc94f-118">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="bc94f-119">In diesem Fall wird der gesamte Leerraum in der XML-Struktur beibehalten.</span><span class="sxs-lookup"><span data-stu-id="bc94f-119">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc94f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc94f-120">See also</span></span>

- [<span data-ttu-id="bc94f-121">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc94f-121">Serializing XML Trees (Visual Basic)</span></span>](serializing-xml-trees.md)
