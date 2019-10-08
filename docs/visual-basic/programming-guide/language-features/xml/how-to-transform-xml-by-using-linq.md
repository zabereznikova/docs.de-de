---
title: 'Vorgehensweise: Transformieren von XML mithilfe von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 08378775f2c30d8ebfcc4f7ceea6fc3ecb2066e5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003262"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Vorgehensweise: Transformieren von XML mithilfe von LINQ (Visual Basic)
[XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) erleichtern das Lesen von XML aus einer Quelle und transformieren dieses in ein neues XML-Format. Sie können LINQ-Abfragen verwenden, um den zu transformierenden Inhalt abzurufen oder um Inhalt in einem vorhandenen Dokument in ein neues XML-Format zu ändern.  
  
 Im Beispiel in diesem Thema wird der Inhalt aus einem XML-Quelldokument in HTML transformiert, das in einem Browser angezeigt werden soll.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a>So transformieren Sie ein XML-Dokument  
  
1. Erstellen Sie in Visual Studio ein neues Visual Basic Projekt in der Projektvorlage **Konsolenanwendung** .  
  
2. Doppelklicken Sie auf die im Projekt erstellte Datei Module1. vb, um den Visual Basic Code zu ändern. Fügen Sie den folgenden Code in das `Sub Main` des Moduls `Module1` ein. Mit diesem Code wird das XML-Quelldokument als <xref:System.Xml.Linq.XDocument>-Objekt erstellt.  
  
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
  
     [Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream @ no__t-0.  
  
3. Fügen Sie nach dem Code zum Erstellen des XML-Quelldokuments den folgenden Code hinzu, um alle \<book-> Elemente aus dem-Objekt abzurufen und in ein HTML-Dokument umzuwandeln. Die Liste der > Elemente \<book wird mithilfe einer LINQ-Abfrage erstellt, die eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten zurückgibt, die das transformierte HTML enthalten. Sie können eingebettete Ausdrücke verwenden, um die Werte aus dem Quelldokument im neuen XML-Format zu platzieren.  
  
     Das resultierende HTML-Dokument wird mithilfe der <xref:System.Xml.Linq.XElement.Save%2A>-Methode in eine Datei geschrieben.  
  
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
  
4. Fügen Sie nach `Sub Main` von `Module1` eine neue Methode (`Sub`) hinzu, um einen \<description-> Knoten in das angegebene HTML-Format umzuwandeln. Diese Methode wird vom Code im vorherigen Schritt aufgerufen und wird verwendet, um das Format der \<description > Elemente beizubehalten.  
  
     Diese Methode ersetzt unter Elemente der \<description >-Elements durch HTML. Die `ReplaceWith`-Methode wird verwendet, um den Speicherort der untergeordneten Elemente beizubehalten. Der transformierte Inhalt der \<description >-Elements ist in einem HTML-Absatz Element (\<P >) enthalten. Die <xref:System.Xml.Linq.XContainer.Nodes%2A>-Eigenschaft wird verwendet, um den transformierten Inhalt des \<description >-Elements abzurufen. Dadurch wird sichergestellt, dass untergeordnete Elemente in den transformierten Inhalt eingeschlossen werden.  
  
     Fügen Sie den folgenden Code nach `Sub Main` von `Module1` hinzu.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)
- [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream @ no__t-0
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
