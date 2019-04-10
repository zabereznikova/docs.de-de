---
title: 'Vorgehensweise: Transformieren von XML mithilfe von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: c34d3988c89e0ce07676e9181200fc039010b50a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324983"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="65aac-102">Vorgehensweise: Transformieren von XML mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65aac-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="65aac-103">[XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) erleichtern das Lesen von XML aus einer Quelle, und in ein neues XML-Format transformieren.</span><span class="sxs-lookup"><span data-stu-id="65aac-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="65aac-104">Sie können profitieren Sie von LINQ-Abfragen zum Abrufen des Inhalts zu transformieren oder Ändern von Inhalt in einem vorhandenen Dokument in ein neues XML-Format.</span><span class="sxs-lookup"><span data-stu-id="65aac-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="65aac-105">Im Beispiel in diesem Thema transformiert die Inhalte von einem XML-Quelldokument in HTML in einem Browser angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="65aac-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="65aac-106">Um ein XML-Dokument zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="65aac-106">To transform an XML document</span></span>  
  
1. <span data-ttu-id="65aac-107">Erstellen Sie in Visual Studio ein neues Visual Basic-Projekt in der **Konsolenanwendung** Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="65aac-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2. <span data-ttu-id="65aac-108">Doppelklicken Sie auf die Datei "Module1.vb" im Projekt so ändern Sie die Visual Basic-Code erstellt.</span><span class="sxs-lookup"><span data-stu-id="65aac-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="65aac-109">Fügen Sie den folgenden Code der `Sub Main` von der `Module1` Modul.</span><span class="sxs-lookup"><span data-stu-id="65aac-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="65aac-110">Dieser Code erstellt das XML-Quelldokument als ein <xref:System.Xml.Linq.XDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="65aac-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
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
  
     <span data-ttu-id="65aac-111">[Vorgehensweise: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="65aac-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3. <span data-ttu-id="65aac-112">Nach dem Code zum Erstellen von XML-Quelldokument, fügen Sie den folgenden Code aus, um alle abzurufen der \<Buch >-Elemente des Objekts und deren Umwandlung in ein HTML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="65aac-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="65aac-113">Die Liste der \<Book > Elemente wird erstellt, indem Sie mithilfe einer LINQ-Abfrage, die eine Auflistung von zurückgibt <xref:System.Xml.Linq.XElement> Objekte, die die transformierte HTML enthalten.</span><span class="sxs-lookup"><span data-stu-id="65aac-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="65aac-114">Sie können eingebettete Ausdrücke verwenden, um die Werte aus dem Quelldokument im neuen XML-Format.</span><span class="sxs-lookup"><span data-stu-id="65aac-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="65aac-115">Die resultierende HTML-Dokument in eine Datei geschrieben wird, mithilfe der <xref:System.Xml.Linq.XElement.Save%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="65aac-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
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
  
4. <span data-ttu-id="65aac-116">Nach dem `Sub Main` von `Module1`, fügen Sie eine neue Methode hinzu (`Sub`) zum Transformieren einer \<Beschreibung > Knoten in das angegebene HTML-Format.</span><span class="sxs-lookup"><span data-stu-id="65aac-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="65aac-117">Diese Methode wird aufgerufen, durch den Code im vorherigen Schritt und wird verwendet, um das Format des beibehalten der \<Beschreibung > Elemente.</span><span class="sxs-lookup"><span data-stu-id="65aac-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="65aac-118">Diese Methode ersetzt die untergeordnete Elemente des der \<Description >-Element mit HTML.</span><span class="sxs-lookup"><span data-stu-id="65aac-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="65aac-119">Die `ReplaceWith` Methode wird verwendet, um den Speicherort der untergeordneten Elemente beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="65aac-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="65aac-120">Den transformierten Inhalt der \<Description >-Element in einer HTML-Abschnitt eingeschlossen wird (\<p >) Element.</span><span class="sxs-lookup"><span data-stu-id="65aac-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="65aac-121">Die <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft wird verwendet, um den Inhalt des transformierten von Abrufen der \<Beschreibung > Element.</span><span class="sxs-lookup"><span data-stu-id="65aac-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="65aac-122">Dadurch wird sichergestellt, dass untergeordnete Elemente in den transformierten Inhalt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="65aac-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="65aac-123">Fügen Sie den folgenden Code nach `Sub Main` von `Module1`.</span><span class="sxs-lookup"><span data-stu-id="65aac-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
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
  
5. <span data-ttu-id="65aac-124">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="65aac-124">Save your changes.</span></span>  
  
6. <span data-ttu-id="65aac-125">Drücken Sie F5, um den Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="65aac-125">Press F5 to run the code.</span></span> <span data-ttu-id="65aac-126">Das resultierende Dokument gespeichert werden wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="65aac-126">The resulting saved document will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65aac-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65aac-127">See also</span></span>

- [<span data-ttu-id="65aac-128">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="65aac-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="65aac-129">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65aac-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="65aac-130">XML</span><span class="sxs-lookup"><span data-stu-id="65aac-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="65aac-131">Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream</span><span class="sxs-lookup"><span data-stu-id="65aac-131">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="65aac-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="65aac-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="65aac-133">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65aac-133">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
