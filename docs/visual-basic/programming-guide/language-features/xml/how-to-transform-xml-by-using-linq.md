---
title: 'Gewusst wie: Umwandeln von XML mithilfe von LINQ (Visual Basic) | Microsoft-Dokumentation'
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
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 12b5bfd059d219a5cb0087e763688d01a75b0533
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="4758a-102">Gewusst wie: Transformieren von XML unter Verwendung von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4758a-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="4758a-103">[XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) vereinfachen das XML aus einer Quelle gelesen und in ein neues XML-Format umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="4758a-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="4758a-104">Sie können Nutzen von LINQ-Abfragen zum Abrufen des Inhalts zu transformieren oder Ändern von Inhalt in einem vorhandenen Dokument in ein neues XML-Format.</span><span class="sxs-lookup"><span data-stu-id="4758a-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="4758a-105">Das Beispiel in diesem Thema transformiert Inhalt aus einem XML-Quelldokument in HTML in einem Browser angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4758a-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="4758a-106">Um ein XML-Dokument zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="4758a-106">To transform an XML document</span></span>  
  
1.  <span data-ttu-id="4758a-107">Erstellen Sie in Visual Studio ein neues Visual Basic-Projekt in der **Konsolenanwendung** -Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="4758a-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2.  <span data-ttu-id="4758a-108">Doppelklicken Sie auf die Datei "Module1.vb" im Projekt so ändern Sie die Visual Basic-Code erstellt.</span><span class="sxs-lookup"><span data-stu-id="4758a-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="4758a-109">Fügen Sie den folgenden Code der `Sub Main` von der `Module1` Modul.</span><span class="sxs-lookup"><span data-stu-id="4758a-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="4758a-110">Dieser Code erstellt das XML-Quelldokument als ein <xref:System.Xml.Linq.XDocument>Objekt.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="4758a-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
    ```vb  
    Dim catalog =   
      <?xml version="1.0"?>  
        <Catalog>  
          <Book id="bk101">  
            <Author>Garghentini, Davide</Author>  
            <Title>XML Developer's Guide</Title>  
            <Price>44.95</Price>  
            <Description>  
              An in-depth look at creating applications  
              with <technology>XML</technology>. For   
              <audience>beginners</audience> or   
              <audience>advanced</audience> developers.  
            </Description>  
          </Book>  
          <Book id="bk331">  
            <Author>Spencer, Phil</Author>  
            <Title>Developing Applications with Visual Basic .NET</Title>  
            <Price>45.95</Price>  
            <Description>  
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     <span data-ttu-id="4758a-111">[Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="4758a-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3.  <span data-ttu-id="4758a-112">Nach dem Code zum Erstellen von XML-Quelldokument, fügen Sie den folgenden Code zum Abrufen von all den \<Buch > Elemente aus dem Objekt und deren Umwandlung in ein HTML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="4758a-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="4758a-113">Die Liste der \<Buch > Elemente wird mithilfe einer LINQ-Abfrage, die eine Auflistung von zurückgibt erstellt <xref:System.Xml.Linq.XElement>Objekte, die die transformierte HTML enthalten.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4758a-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="4758a-114">Eingebettete Ausdrücke können Sie die Werte aus dem Quelldokument in das neue XML-Format eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4758a-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="4758a-115">Die resultierende HTML-Dokument in eine Datei geschrieben wird, mithilfe der <xref:System.Xml.Linq.XElement.Save%2A>-Methode.</xref:System.Xml.Linq.XElement.Save%2A></span><span class="sxs-lookup"><span data-stu-id="4758a-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
    ```vb  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4.  <span data-ttu-id="4758a-116">Nach `Sub Main` von `Module1`, fügen Sie eine neue Methode (`Sub`) zum Transformieren einer \<Beschreibung >-Knoten in das angegebene HTML-Format.</span><span class="sxs-lookup"><span data-stu-id="4758a-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="4758a-117">Diese Methode wird aufgerufen, durch den Code im vorherigen Schritt, und wird verwendet, um das Format des beibehalten der \<Beschreibung > Elemente.</span><span class="sxs-lookup"><span data-stu-id="4758a-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="4758a-118">Diese Methode ersetzt die untergeordnete Elemente von der \<Beschreibung > Element durch HTML-Code.</span><span class="sxs-lookup"><span data-stu-id="4758a-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="4758a-119">Die `ReplaceWith` -Methode verwendet, um die Position der Unterelemente zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4758a-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="4758a-120">Den transformierten Inhalt von der \<Beschreibung > Element befindet sich auf einer HTML-Absatz (\<p >) Element.</span><span class="sxs-lookup"><span data-stu-id="4758a-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="4758a-121">Die <xref:System.Xml.Linq.XContainer.Nodes%2A>Eigenschaft wird verwendet, um den transformierten Inhalt Abrufen der \<Beschreibung > Element.</xref:System.Xml.Linq.XContainer.Nodes%2A></span><span class="sxs-lookup"><span data-stu-id="4758a-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="4758a-122">Dadurch wird sichergestellt, dass Unterelemente im umgewandelten Inhalt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4758a-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="4758a-123">Fügen Sie den folgenden Code nach `Sub Main` von `Module1`.</span><span class="sxs-lookup"><span data-stu-id="4758a-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
    ```vb  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5.  <span data-ttu-id="4758a-124">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="4758a-124">Save your changes.</span></span>  
  
6.  <span data-ttu-id="4758a-125">Drücken Sie F5, um den Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4758a-125">Press F5 to run the code.</span></span> <span data-ttu-id="4758a-126">Das resultierende Dokument gespeichert wird folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="4758a-126">The resulting saved document will resemble the following:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4758a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4758a-127">See Also</span></span>  
 <span data-ttu-id="4758a-128">[XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="4758a-128">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="4758a-129"> [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="4758a-129"> [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span></span>  
<span data-ttu-id="4758a-130"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="4758a-130"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="4758a-131"> [Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span><span class="sxs-lookup"><span data-stu-id="4758a-131"> [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span></span>  
<span data-ttu-id="4758a-132"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="4758a-132"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="4758a-133"> [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="4758a-133"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>

