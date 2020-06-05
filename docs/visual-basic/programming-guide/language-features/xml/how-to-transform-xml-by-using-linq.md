---
title: 'Vorgehensweise: Transformieren von XML unter Verwendung von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: dab394ec45567589e002b5d2ac76ec19fb0f76c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374881"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="4a6ec-102">Gewusst wie: Transformieren von XML unter Verwendung von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a6ec-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="4a6ec-103">[XML-Literale](../../../language-reference/xml-literals/index.md) erleichtern das Lesen von XML aus einer Quelle und transformieren dieses in ein neues XML-Format.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-103">[XML Literals](../../../language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="4a6ec-104">Sie können LINQ-Abfragen verwenden, um den zu transformierenden Inhalt abzurufen oder um Inhalt in einem vorhandenen Dokument in ein neues XML-Format zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>

<span data-ttu-id="4a6ec-105">Im Beispiel in diesem Thema wird der Inhalt aus einem XML-Quelldokument in HTML transformiert, das in einem Browser angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a><span data-ttu-id="4a6ec-106">So transformieren Sie ein XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="4a6ec-106">To transform an XML document</span></span>

1. <span data-ttu-id="4a6ec-107">Erstellen Sie in Visual Studio ein neues Visual Basic Projekt in der Projektvorlage **Konsolenanwendung** .</span><span class="sxs-lookup"><span data-stu-id="4a6ec-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>

2. <span data-ttu-id="4a6ec-108">Doppelklicken Sie auf die im Projekt erstellte Datei Module1. vb, um den Visual Basic Code zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="4a6ec-109">Fügen Sie dem des Moduls den folgenden Code hinzu `Sub Main` `Module1` .</span><span class="sxs-lookup"><span data-stu-id="4a6ec-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="4a6ec-110">Mit diesem Code wird das XML-Quelldokument als- <xref:System.Xml.Linq.XDocument> Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>

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

     <span data-ttu-id="4a6ec-111">Gewusst [wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream](how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="4a6ec-111">[How to: Load XML from a File, String, or Stream](how-to-load-xml-from-a-file-string-or-stream.md).</span></span>

3. <span data-ttu-id="4a6ec-112">Fügen Sie nach dem Code zum Erstellen des XML-Quelldokuments den folgenden Code hinzu, um alle \<Book> Elemente aus dem-Objekt abzurufen und in ein HTML-Dokument umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="4a6ec-113">Die Liste der \<Book> Elemente wird mithilfe einer LINQ-Abfrage erstellt, die eine Auflistung von-Objekten zurückgibt, die <xref:System.Xml.Linq.XElement> das transformierte HTML enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="4a6ec-114">Sie können eingebettete Ausdrücke verwenden, um die Werte aus dem Quelldokument im neuen XML-Format zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>

     <span data-ttu-id="4a6ec-115">Das resultierende HTML-Dokument wird mithilfe der-Methode in eine Datei geschrieben <xref:System.Xml.Linq.XElement.Save%2A> .</span><span class="sxs-lookup"><span data-stu-id="4a6ec-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>

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

4. <span data-ttu-id="4a6ec-116">`Sub Main` `Module1` Fügen Sie nach dem von eine neue Methode () hinzu, `Sub` um einen \<Description> Knoten in das angegebene HTML-Format umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="4a6ec-117">Diese Methode wird vom Code im vorherigen Schritt aufgerufen und wird verwendet, um das Format der \<Description> Elemente beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>

     <span data-ttu-id="4a6ec-118">Diese Methode ersetzt unter Elemente des \<Description> Elements durch HTML.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="4a6ec-119">Die- `ReplaceWith` Methode wird verwendet, um den Speicherort der untergeordneten Elemente beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="4a6ec-120">Der transformierte Inhalt des- \<Description> Elements ist in einem HTML-Absatz \<p> Element () enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="4a6ec-121">Die- <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft wird zum Abrufen des transformierten Inhalts des- \<Description> Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="4a6ec-122">Dadurch wird sichergestellt, dass untergeordnete Elemente in den transformierten Inhalt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-122">This ensures that sub-elements are included in the transformed content.</span></span>

     <span data-ttu-id="4a6ec-123">Fügen Sie den folgenden Code nach hinzu `Sub Main` `Module1` .</span><span class="sxs-lookup"><span data-stu-id="4a6ec-123">Add the following code after `Sub Main` of `Module1`.</span></span>

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

5. <span data-ttu-id="4a6ec-124">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-124">Save your changes.</span></span>

6. <span data-ttu-id="4a6ec-125">Drücken Sie F5, um den Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4a6ec-125">Press F5 to run the code.</span></span> <span data-ttu-id="4a6ec-126">Das resultierende gespeicherte Dokument ähnelt dem folgenden:</span><span class="sxs-lookup"><span data-stu-id="4a6ec-126">The resulting saved document will resemble the following:</span></span>

    ```html
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

## <a name="see-also"></a><span data-ttu-id="4a6ec-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a6ec-127">See also</span></span>

- [<span data-ttu-id="4a6ec-128">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="4a6ec-128">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
- [<span data-ttu-id="4a6ec-129">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a6ec-129">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="4a6ec-130">XML</span><span class="sxs-lookup"><span data-stu-id="4a6ec-130">XML</span></span>](index.md)
- [<span data-ttu-id="4a6ec-131">Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream</span><span class="sxs-lookup"><span data-stu-id="4a6ec-131">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="4a6ec-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="4a6ec-132">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="4a6ec-133">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a6ec-133">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
