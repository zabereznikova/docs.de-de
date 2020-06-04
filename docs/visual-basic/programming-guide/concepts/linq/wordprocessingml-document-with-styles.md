---
title: WordprocessingML-Dokument mit Styles2
ms.date: 07/20/2015
ms.assetid: a9136e4d-c368-4661-8049-7d45c679a236
ms.openlocfilehash: caf80014077bf57dc1ffb8eaeac6390cf4258015
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403549"
---
# <a name="wordprocessingml-document-with-styles"></a><span data-ttu-id="e94ef-102">WordprocessingML-Dokumente mit Formatvorlagen</span><span class="sxs-lookup"><span data-stu-id="e94ef-102">WordprocessingML Document with Styles</span></span>
<span data-ttu-id="e94ef-103">Kompliziertere WordprocessingML-Dokumente besitzen Absätze, die mit Formatvorlagen formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="e94ef-103">More complicated WordprocessingML documents have paragraphs that are formatted with styles.</span></span>  
  
 <span data-ttu-id="e94ef-104">Im Folgenden finden Sie einige hilfreiche Hinweise zum Aufbau von WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="e94ef-104">A few notes about the makeup of WordprocessingML documents are helpful.</span></span> <span data-ttu-id="e94ef-105">WordprocessingML-Dokumente werden in Paketen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e94ef-105">WordprocessingML documents are stored in packages.</span></span> <span data-ttu-id="e94ef-106">Die Pakete bestehen aus mehreren Teilen (der Begriff "Teil" hat im Zusammenhang mit Paketen eine explizite Bedeutung; ganz allgemein handelt es sich bei den Teilen um Dateien, die zu einem Paket zusammengezippt wurden).</span><span class="sxs-lookup"><span data-stu-id="e94ef-106">Packages have multiple parts (parts have an explicit meaning when used in the context of packages; essentially, parts are files that are zipped together to comprise a package).</span></span> <span data-ttu-id="e94ef-107">Wenn ein Dokument Absätze enthält, die mit Formatvorlagen formatiert sind, gibt es einen Dokumentteil, der die Absätze enthält, denen Formatvorlagen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="e94ef-107">If a document contains paragraphs that are formatted with styles, there will be a document part that contains paragraphs that have styles applied to them.</span></span> <span data-ttu-id="e94ef-108">Außerdem gibt es einen Formatvorlagenteil, der die Formatvorlagen enthält, auf die das Dokument zurückgreift.</span><span class="sxs-lookup"><span data-stu-id="e94ef-108">There will also be a style part that contains the styles that are referred to by the document.</span></span>  
  
 <span data-ttu-id="e94ef-109">Beim Zugriff auf Pakete ist es wichtig, dass Sie dies über die Beziehungen zwischen den Teilen und nicht über einen beliebigen Pfad tun.</span><span class="sxs-lookup"><span data-stu-id="e94ef-109">When accessing packages, it is important that you do so through the relationships between parts, rather than using an arbitrary path.</span></span> <span data-ttu-id="e94ef-110">Auf dieses Problem wird zwar im Tutorial „Bearbeiten von Inhalten in einem WordprocessingML-Dokument“ nicht eingegangen, die Beispielprogramme in diesem Tutorial zeigen aber die korrekte Herangehensweise.</span><span class="sxs-lookup"><span data-stu-id="e94ef-110">This issue is beyond the scope of the Manipulating Content in a WordprocessingML Document tutorial, but the example programs that are included in this tutorial demonstrate the correct approach.</span></span>  
  
## <a name="a-document-that-uses-styles"></a><span data-ttu-id="e94ef-111">Ein Dokument mit Formatvorlagen</span><span class="sxs-lookup"><span data-stu-id="e94ef-111">A Document that Uses Styles</span></span>  
 <span data-ttu-id="e94ef-112">Das im Thema [Form von WordprocessingML Documents (Visual Basic)](shape-of-wordprocessingml-documents.md) gezeigte WordML-Beispiel ist ein sehr einfaches Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e94ef-112">The WordML example presented in the [Shape of WordprocessingML Documents (Visual Basic)](shape-of-wordprocessingml-documents.md) topic is a very simple one.</span></span> <span data-ttu-id="e94ef-113">Das folgende Dokument ist etwas komplizierter: Es besitzt Absätze, die mit Formatvorlagen formatiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e94ef-113">The following document is more complicated: It has paragraphs that are formatted with styles.</span></span> <span data-ttu-id="e94ef-114">Die einfachste Möglichkeit, den XML-Code eines Office Open XML-Dokuments anzuzeigen, besteht darin, das [Beispiel auszuführen, das Office Open XML-Dokument Teile (Visual Basic) ausgibt](example-that-outputs-office-open-xml-document-parts.md).</span><span class="sxs-lookup"><span data-stu-id="e94ef-114">The easiest way to see the XML that makes up an Office Open XML document is to run the [Example that Outputs Office Open XML Document Parts (Visual Basic)](example-that-outputs-office-open-xml-document-parts.md).</span></span>  
  
 <span data-ttu-id="e94ef-115">Im folgenden Dokument ist der erste Absatz mit der Formatvorlage `Heading1` formatiert worden.</span><span class="sxs-lookup"><span data-stu-id="e94ef-115">In the following document, the first paragraph has the style `Heading1`.</span></span> <span data-ttu-id="e94ef-116">Eine Reihe von Absätzen sind mit der Standardformatvorlage formatiert worden.</span><span class="sxs-lookup"><span data-stu-id="e94ef-116">There are a number of paragraphs that have the default style.</span></span> <span data-ttu-id="e94ef-117">Einigen Absätzen wurde die Formatvorlage `Code` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e94ef-117">There are also a number of paragraphs that have the style `Code`.</span></span> <span data-ttu-id="e94ef-118">Aufgrund dieser relativen Komplexität ist dieses Dokument für das Analysieren mit LINQ to XML interessanter.</span><span class="sxs-lookup"><span data-stu-id="e94ef-118">Because of this relative complexity, this is a more interesting document to parse with LINQ to XML.</span></span>  
  
 <span data-ttu-id="e94ef-119">In den Absätzen, die nicht mit der Standardformatvorlage formatiert sind, besitzen die Absatzelemente ein untergeordnetes Element mit dem Namen `w:pPr`, das wiederum ein untergeordnetes Element namens `w:pStyle` besitzt.</span><span class="sxs-lookup"><span data-stu-id="e94ef-119">In those paragraphs with non-default styles, the paragraph elements have a child element named `w:pPr`, which in turn has a child element `w:pStyle`.</span></span> <span data-ttu-id="e94ef-120">Dieses Element verfügt über ein Attribut, `w:val`, das den Namen der Formatvorlage enthält.</span><span class="sxs-lookup"><span data-stu-id="e94ef-120">That element has an attribute, `w:val`, which contains the style name.</span></span> <span data-ttu-id="e94ef-121">Wenn ein Absatz mit der Standardformatvorlage formatiert ist, bedeutet das, dass das Absatzelement kein untergeordnetes `w:p.Pr`-Element besitzt.</span><span class="sxs-lookup"><span data-stu-id="e94ef-121">If the paragraph has the default style, it means that the paragraph element does not have a `w:p.Pr` child element.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<w:document  
    xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:o="urn:schemas-microsoft-com:office:office"  
    xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
    xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
    xmlns:v="urn:schemas-microsoft-com:vml"  
    xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
    xmlns:w10="urn:schemas-microsoft-com:office:word"  
    xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
    xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Heading1" />  
      </w:pPr>  
      <w:r>  
        <w:t>Parsing WordprocessingML with LINQ to XML</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>The following example prints to the console.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>using System;</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>class Program {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    public static void </w:t>  
      </w:r>  
      <w:smartTag w:uri="urn:schemas-microsoft-com:office:smarttags" w:element="place">  
        <w:r w:rsidRPr="00876F34">  
          <w:t>Main</w:t>  
        </w:r>  
      </w:smartTag>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>(string[] args) {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">        Console.WriteLine("Hello World");</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    }</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>}</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>This example produces the following output:</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>Hello World</w:t>  
      </w:r>  
    </w:p>  
    <w:sectPr w:rsidR="00A75AE0" w:rsidSect="00A75AE0">  
      <w:pgSz w:w="12240" w:h="15840" />  
      <w:pgMar w:top="1440" w:right="1800" w:bottom="1440" w:left="1800" w:header="720" w:footer="720" w:gutter="0" />  
      <w:cols w:space="720" />  
      <w:docGrid w:linePitch="360" />  
    </w:sectPr>  
  </w:body>  
</w:document>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e94ef-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e94ef-122">See also</span></span>

- [<span data-ttu-id="e94ef-123">Details zu Office Open XML-WordprocessingML-Dokumenten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e94ef-123">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](details-of-office-open-xml-wordprocessingml-documents.md)
