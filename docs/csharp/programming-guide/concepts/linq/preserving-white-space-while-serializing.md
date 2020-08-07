---
title: Beibehalten von Leerraum beim Serialisieren3
description: Erfahren Sie, wie Sie mithilfe von Methoden in den Klassen „XElement“ und „XDocument“ das Leerraumverhalten beim Serialisieren von XML-Strukturen steuern können.
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 01e68671e2fde1a2b5b1d0bc429841077ba0205f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303412"
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="60618-103">Beibehalten von Leerzeichen beim Serialisieren</span><span class="sxs-lookup"><span data-stu-id="60618-103">Preserving White Space While Serializing</span></span>
<span data-ttu-id="60618-104">In diesem Thema wird beschrieben, wie Sie das Leerraumverhalten beim Serialisieren von XML-Strukturen steuern können.</span><span class="sxs-lookup"><span data-stu-id="60618-104">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="60618-105">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="60618-105">A common scenario is to read indented XML, create an in-memory XML tree without any white-space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="60618-106">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="60618-106">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="60618-107">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60618-107">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="60618-108">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="60618-108">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="60618-109">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="60618-109">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="60618-110">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="60618-110">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="60618-111">Leerraumverhalten von Methoden, die XML-Strukturen serialisieren</span><span class="sxs-lookup"><span data-stu-id="60618-111">White-Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="60618-112">Die folgenden Methoden in den Klassen <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument> serialisieren eine XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="60618-112">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="60618-113">Sie können XML-Strukturen in eine Datei, in einen <xref:System.IO.TextReader> oder in einen <xref:System.Xml.XmlReader> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="60618-113">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="60618-114">Die `ToString`-Methode nimmt eine Serialisierung in eine Zeichenfolge vor.</span><span class="sxs-lookup"><span data-stu-id="60618-114">The `ToString` method serializes to a string.</span></span>  
  
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
- [<span data-ttu-id="60618-115">XElement.ToString()</span><span class="sxs-lookup"><span data-stu-id="60618-115">XElement.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
- [<span data-ttu-id="60618-116">XDocument.ToString()</span><span class="sxs-lookup"><span data-stu-id="60618-116">XDocument.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
 <span data-ttu-id="60618-117">Wenn die Methode nicht <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, formatiert die Methode den serialisierten XML-Code, indem sie ihn mit Einzügen versieht.</span><span class="sxs-lookup"><span data-stu-id="60618-117">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="60618-118">In diesem Fall wird der gesamte nicht signifikante Leerraum in der XML-Struktur verworfen.</span><span class="sxs-lookup"><span data-stu-id="60618-118">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="60618-119">Wenn die Methode <xref:System.Xml.Linq.SaveOptions> als Argument akzeptiert, können Sie angeben, dass der serialisierte XML-Code nicht formatiert (eingerückt) werden soll.</span><span class="sxs-lookup"><span data-stu-id="60618-119">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="60618-120">In diesem Fall wird der gesamte Leerraum in der XML-Struktur beibehalten.</span><span class="sxs-lookup"><span data-stu-id="60618-120">In this case, all white space in the XML tree is preserved.</span></span>  
