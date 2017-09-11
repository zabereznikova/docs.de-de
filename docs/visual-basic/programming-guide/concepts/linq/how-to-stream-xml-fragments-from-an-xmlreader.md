---
title: 'Gewusst wie: Streamen von XML-Fragmenten aus einem XmlReader (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a><span data-ttu-id="0a469-102">Gewusst wie: Streamen von XML-Fragmenten aus einem XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a469-102">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="0a469-103">Wenn Sie große XML-Dateien verarbeiten müssen, kann u. U. nicht die gesamte XML-Struktur in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0a469-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="0a469-104">In diesem Thema veranschaulicht, wie mithilfe einer <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> Fragmente Streamen</span><span class="sxs-lookup"><span data-stu-id="0a469-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="0a469-105">Eine der effektivsten Methoden verwenden ein <xref:System.Xml.XmlReader>Lesen <xref:System.Xml.Linq.XElement>Objekten ist eine eigene benutzerdefinierte Achsenmethode schreiben.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="0a469-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="0a469-106">Achsenmethode gibt in der Regel eine Auflistung wie z. B. <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>, wie im Beispiel in diesem Thema gezeigt.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0a469-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="0a469-107">In der benutzerdefinierten Achsenmethode, nach der Erstellung von XML-Fragment durch Aufrufen der <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode zurückgegeben wird, die Auflistung mit `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="0a469-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="0a469-108">Auf diese Weise versehen Sie Ihre benutzerdefinierte Achsenmethode mit der Semantik für eine verzögerte Ausführung.</span><span class="sxs-lookup"><span data-stu-id="0a469-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="0a469-109">Beim Erstellen einer XML-Struktur aus einem <xref:System.Xml.XmlReader>-Objekt, das <xref:System.Xml.XmlReader>muss auf einem Element positioniert werden.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="0a469-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="0a469-110">Die <xref:System.Xml.Linq.XNode.ReadFrom%2A>Methode gibt keinen zurück, bis sie das Endtag des Elements gelesen hat.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="0a469-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="0a469-111">Wenn Sie eine Teilstruktur erstellen möchten, instanziieren Sie ein <xref:System.Xml.XmlReader>, positionieren Sie den Reader auf dem Knoten, die Sie zum konvertieren möchten eine <xref:System.Xml.Linq.XElement>Struktur, und erstellen Sie die <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="0a469-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="0a469-112">Das Thema [How to: Stream XML-Fragmenten mit Zugriff auf Headerinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) enthält Informationen und ein Beispiel dafür, wie komplexere Dokumente gestreamt.</span><span class="sxs-lookup"><span data-stu-id="0a469-112">The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="0a469-113">Das Thema [Gewusst wie: Ausführen Streaming Transformieren von großen XML-Dokumenten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) enthält ein Beispiel der Verwendung von LINQ to XML extrem große XML-Dokumente zu transformieren, Beibehaltung einer geringen speicherbeanspruchung.</span><span class="sxs-lookup"><span data-stu-id="0a469-113">The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a469-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a469-114">Example</span></span>  
 <span data-ttu-id="0a469-115">Dieses Beispiel erstellt eine benutzerdefinierte Achsenmethode.</span><span class="sxs-lookup"><span data-stu-id="0a469-115">This example creates a custom axis method.</span></span> <span data-ttu-id="0a469-116">Zum Abfragen kann eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a469-116">You can query it by using a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query.</span></span> <span data-ttu-id="0a469-117">Die benutzerdefinierte Achsenmethode `StreamRootChildDoc` eignet sich vor allem zum Lesen eines Dokuments, das ein sich wiederholendes `Child`-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="0a469-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
<span data-ttu-id="0a469-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0a469-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="0a469-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0a469-119">This example produces the following output:</span></span>  
  
<span data-ttu-id="0a469-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0a469-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="0a469-121">In diesem Beispiel ist das Quelldokument sehr klein.</span><span class="sxs-lookup"><span data-stu-id="0a469-121">In this example, the source document is very small.</span></span> <span data-ttu-id="0a469-122">Dieses Beispiel würde aber auch dann wenig Speicher beanspruchen, wenn das Quelldokument Millionen `Child`-Elemente enthielte.</span><span class="sxs-lookup"><span data-stu-id="0a469-122">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a469-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a469-123">See Also</span></span>  
 <span data-ttu-id="0a469-124">[Exemplarische Vorgehensweise: Implementieren von IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span><span class="sxs-lookup"><span data-stu-id="0a469-124">[Walkthrough: Implementing IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span></span>  
<span data-ttu-id="0a469-125"> [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="0a469-125"> [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span></span>
