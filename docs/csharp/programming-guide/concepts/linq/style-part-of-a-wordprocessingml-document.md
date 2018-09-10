---
title: Formatvorlagenteil eines WordprocessingML-Dokument1
ms.date: 07/20/2015
ms.assetid: 5458bccf-3898-4661-904b-7d280c9239a9
ms.openlocfilehash: 96ed7445379d9a8ca64250ef4d923786555a3882
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44179597"
---
# <a name="style-part-of-a-wordprocessingml-document"></a><span data-ttu-id="a42b6-102">Absatzformatteil eines WordprocessingML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="a42b6-102">Style Part of a WordprocessingML Document</span></span>
<span data-ttu-id="a42b6-103">In diesem Thema wird ein Beispiel für den Formatvorlagenteil des Office Open XML-WordprocessingML-Dokuments gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a42b6-103">This topic shows an example of the style part of the Office Open XML WordprocessingML document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a42b6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a42b6-104">Example</span></span>  
 <span data-ttu-id="a42b6-105">Das folgende Beispiel zeigt den XML-Code, der den Formatvorlagenteil des Office Open XML-WordprocessingML-Dokuments darstellt.</span><span class="sxs-lookup"><span data-stu-id="a42b6-105">The following example is the XML that makes up the style part of an Office Open XML WordprocessingML document.</span></span>  
  
 <span data-ttu-id="a42b6-106">Das Standardabsatzformat verfügt über ein Element mit dem folgenden Starttag:</span><span class="sxs-lookup"><span data-stu-id="a42b6-106">The default paragraph style has an element with the following opening tag:</span></span>  
  
```  
<w:style w:type="paragraph" w:default="1" w:styleId="Normal">  
```  
  
 <span data-ttu-id="a42b6-107">Sie müssen diese Informationen kennen, wenn Sie die Abfrage zum Ermitteln der Standardformatvorlagen-ID schreiben, damit die Abfrage das Format von Absätzen mit der Standardformatvorlage identifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="a42b6-107">You need to know this information when you write the query to find the default style identifier, so that the query can identify the style of paragraphs that have the default style.</span></span>  
  
 <span data-ttu-id="a42b6-108">Beachten Sie, dass diese Dokumente im Vergleich zu Dokumenten, wie sie typischerweise von Microsoft Word generiert werden, sehr einfach gehalten sind.</span><span class="sxs-lookup"><span data-stu-id="a42b6-108">Note that these documents are very simple when compared to typical documents that Microsoft Word generates.</span></span> <span data-ttu-id="a42b6-109">In vielen Fällen speichert Word viele weitere Angaben, zusätzliche Formatierungsinformationen und Metadaten.</span><span class="sxs-lookup"><span data-stu-id="a42b6-109">In many cases, Word saves a great deal of additional information, additional formatting and metadata.</span></span> <span data-ttu-id="a42b6-110">Darüber hinaus formatiert Word die Zeilen nicht so übersichtlich wie in diesem Beispiel. Der XML-Code wird ohne jeden Einzug gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a42b6-110">Furthermore, Word does not format the lines to be easily readable as in this example; instead, the XML is saved without indentation.</span></span> <span data-ttu-id="a42b6-111">Alle WordprocessingML-Dokumente haben jedoch dieselbe grundsätzliche XML-Form.</span><span class="sxs-lookup"><span data-stu-id="a42b6-111">However, all WordprocessingML documents share the same basic XML shape.</span></span> <span data-ttu-id="a42b6-112">Deswegen funktionieren die in dieser Dokumentation präsentierten Abfragen auch mit komplizierteren Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="a42b6-112">Because of this, the queries presented in this tutorial will work with more complicated documents.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<w:styles  
    xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
    xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  <w:docDefaults>  
    <w:rPrDefault>  
      <w:rPr>  
        <w:rFonts  
            w:ascii="Times New Roman"  
            w:eastAsia="Times New Roman"  
            w:hAnsi="Times New Roman"  
            w:cs="Times New Roman" />  
        <w:sz w:val="22" />  
        <w:szCs w:val="22" />  
        <w:lang w:val="en-US" w:eastAsia="en-US" w:bidi="ar-SA" />  
      </w:rPr>  
    </w:rPrDefault>  
    <w:pPrDefault />  
  </w:docDefaults>  
  <w:style w:type="paragraph" w:default="1" w:styleId="Normal">  
    <w:name w:val="Normal" />  
    <w:qFormat />  
    <w:rPr>  
      <w:sz w:val="24" />  
      <w:szCs w:val="24" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="paragraph" w:styleId="Heading1">  
    <w:name w:val="heading 1" />  
    <w:basedOn w:val="Normal" />  
    <w:next w:val="Normal" />  
    <w:link w:val="Heading1Char" />  
    <w:uiPriority w:val="99" />  
    <w:qFormat />  
    <w:rsid w:val="006027C7" />  
    <w:pPr>  
      <w:keepNext />  
      <w:spacing w:before="240" w:after="60" />  
      <w:outlineLvl w:val="0" />  
    </w:pPr>  
    <w:rPr>  
      <w:rFonts w:ascii="Arial" w:hAnsi="Arial" w:cs="Arial" />  
      <w:b />  
      <w:bCs />  
      <w:kern w:val="32" />  
      <w:sz w:val="32" />  
      <w:szCs w:val="32" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="character" w:default="1" w:styleId="DefaultParagraphFont">  
    <w:name w:val="Default Paragraph Font" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
  </w:style>  
  <w:style w:type="table" w:default="1" w:styleId="TableNormal">  
    <w:name w:val="Normal Table" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
    <w:unhideWhenUsed />  
    <w:qFormat />  
    <w:tblPr>  
      <w:tblInd w:w="0" w:type="dxa" />  
      <w:tblCellMar>  
        <w:top w:w="0" w:type="dxa" />  
        <w:left w:w="108" w:type="dxa" />  
        <w:bottom w:w="0" w:type="dxa" />  
        <w:right w:w="108" w:type="dxa" />  
      </w:tblCellMar>  
    </w:tblPr>  
  </w:style>  
  <w:style w:type="numbering" w:default="1" w:styleId="NoList">  
    <w:name w:val="No List" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
    <w:unhideWhenUsed />  
  </w:style>  
  <w:style w:type="character" w:customStyle="1" w:styleId="Heading1Char">  
    <w:name w:val="Heading 1 Char" />  
    <w:basedOn w:val="DefaultParagraphFont" />  
    <w:link w:val="Heading1" />  
    <w:uiPriority w:val="9" />  
    <w:rsid w:val="009765E3" />  
    <w:rPr>  
      <w:rFonts  
          w:asciiTheme="majorHAnsi"  
          w:eastAsiaTheme="majorEastAsia"  
          w:hAnsiTheme="majorHAnsi"  
          w:cstheme="majorBidi" />  
      <w:b />  
      <w:bCs />  
      <w:kern w:val="32" />  
      <w:sz w:val="32" />  
      <w:szCs w:val="32" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="paragraph" w:customStyle="1" w:styleId="Code">  
    <w:name w:val="Code" />  
    <w:aliases w:val="c" />  
    <w:uiPriority w:val="99" />  
    <w:rsid w:val="006027C7" />  
    <w:pPr>  
      <w:spacing w:after="60" w:line="300" w:lineRule="exact" />  
    </w:pPr>  
    <w:rPr>  
      <w:rFonts w:ascii="Courier New" w:hAnsi="Courier New" />  
      <w:noProof />  
      <w:color w:val="000080" />  
      <w:sz w:val="20" />  
      <w:szCs w:val="20" />  
    </w:rPr>  
  </w:style>  
</w:styles>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a42b6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a42b6-113">See Also</span></span>

- [<span data-ttu-id="a42b6-114">Details of Office Open XML WordprocessingML Documents (C#) (Details eines Office Open-XML-WordprocessingML-Dokuments (C#))</span><span class="sxs-lookup"><span data-stu-id="a42b6-114">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)
