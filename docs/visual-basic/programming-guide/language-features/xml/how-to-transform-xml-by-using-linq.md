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
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Gewusst wie: Transformieren von XML unter Verwendung von LINQ (Visual Basic)

[XML-Literale](../../../language-reference/xml-literals/index.md) erleichtern das Lesen von XML aus einer Quelle und transformieren dieses in ein neues XML-Format. Sie können LINQ-Abfragen verwenden, um den zu transformierenden Inhalt abzurufen oder um Inhalt in einem vorhandenen Dokument in ein neues XML-Format zu ändern.

Im Beispiel in diesem Thema wird der Inhalt aus einem XML-Quelldokument in HTML transformiert, das in einem Browser angezeigt werden soll.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a>So transformieren Sie ein XML-Dokument

1. Erstellen Sie in Visual Studio ein neues Visual Basic Projekt in der Projektvorlage **Konsolenanwendung** .

2. Doppelklicken Sie auf die im Projekt erstellte Datei Module1. vb, um den Visual Basic Code zu ändern. Fügen Sie dem des Moduls den folgenden Code hinzu `Sub Main` `Module1` . Mit diesem Code wird das XML-Quelldokument als- <xref:System.Xml.Linq.XDocument> Objekt erstellt.

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

     Gewusst [wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream](how-to-load-xml-from-a-file-string-or-stream.md).

3. Fügen Sie nach dem Code zum Erstellen des XML-Quelldokuments den folgenden Code hinzu, um alle \<Book> Elemente aus dem-Objekt abzurufen und in ein HTML-Dokument umzuwandeln. Die Liste der \<Book> Elemente wird mithilfe einer LINQ-Abfrage erstellt, die eine Auflistung von-Objekten zurückgibt, die <xref:System.Xml.Linq.XElement> das transformierte HTML enthalten. Sie können eingebettete Ausdrücke verwenden, um die Werte aus dem Quelldokument im neuen XML-Format zu platzieren.

     Das resultierende HTML-Dokument wird mithilfe der-Methode in eine Datei geschrieben <xref:System.Xml.Linq.XElement.Save%2A> .

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

4. `Sub Main` `Module1` Fügen Sie nach dem von eine neue Methode () hinzu, `Sub` um einen \<Description> Knoten in das angegebene HTML-Format umzuwandeln. Diese Methode wird vom Code im vorherigen Schritt aufgerufen und wird verwendet, um das Format der \<Description> Elemente beizubehalten.

     Diese Methode ersetzt unter Elemente des \<Description> Elements durch HTML. Die- `ReplaceWith` Methode wird verwendet, um den Speicherort der untergeordneten Elemente beizubehalten. Der transformierte Inhalt des- \<Description> Elements ist in einem HTML-Absatz \<p> Element () enthalten. Die- <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft wird zum Abrufen des transformierten Inhalts des- \<Description> Elements verwendet. Dadurch wird sichergestellt, dass untergeordnete Elemente in den transformierten Inhalt eingeschlossen werden.

     Fügen Sie den folgenden Code nach hinzu `Sub Main` `Module1` .

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

5. Speichern Sie die Änderungen.

6. Drücken Sie F5, um den Code auszuführen. Das resultierende gespeicherte Dokument ähnelt dem folgenden:

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

## <a name="see-also"></a>Weitere Informationen

- [XML-Literale](../../../language-reference/xml-literals/index.md)
- [Bearbeiten von XML in Visual Basic](manipulating-xml.md)
- [XML](index.md)
- [Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Einführung in LINQ in Visual Basic](../linq/introduction-to-linq.md)
