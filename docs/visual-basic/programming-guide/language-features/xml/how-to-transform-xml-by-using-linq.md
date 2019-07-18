---
title: 'Vorgehensweise: Transformieren von XML mithilfe von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: c34d3988c89e0ce07676e9181200fc039010b50a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028433"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Vorgehensweise: Transformieren von XML mithilfe von LINQ (Visual Basic)
[XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) erleichtern das Lesen von XML aus einer Quelle, und in ein neues XML-Format transformieren. Sie können profitieren Sie von LINQ-Abfragen zum Abrufen des Inhalts zu transformieren oder Ändern von Inhalt in einem vorhandenen Dokument in ein neues XML-Format.  
  
 Im Beispiel in diesem Thema transformiert die Inhalte von einem XML-Quelldokument in HTML in einem Browser angezeigt werden.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a>Um ein XML-Dokument zu transformieren.  
  
1. Erstellen Sie in Visual Studio ein neues Visual Basic-Projekt in der **Konsolenanwendung** Projektvorlage.  
  
2. Doppelklicken Sie auf die Datei "Module1.vb" im Projekt so ändern Sie die Visual Basic-Code erstellt. Fügen Sie den folgenden Code der `Sub Main` von der `Module1` Modul. Dieser Code erstellt das XML-Quelldokument als ein <xref:System.Xml.Linq.XDocument> Objekt.  
  
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
  
     [Vorgehensweise: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).  
  
3. Nach dem Code zum Erstellen von XML-Quelldokument, fügen Sie den folgenden Code aus, um alle abzurufen der \<Buch >-Elemente des Objekts und deren Umwandlung in ein HTML-Dokument. Die Liste der \<Book > Elemente wird erstellt, indem Sie mithilfe einer LINQ-Abfrage, die eine Auflistung von zurückgibt <xref:System.Xml.Linq.XElement> Objekte, die die transformierte HTML enthalten. Sie können eingebettete Ausdrücke verwenden, um die Werte aus dem Quelldokument im neuen XML-Format.  
  
     Die resultierende HTML-Dokument in eine Datei geschrieben wird, mithilfe der <xref:System.Xml.Linq.XElement.Save%2A> Methode.  
  
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
  
4. Nach dem `Sub Main` von `Module1`, fügen Sie eine neue Methode hinzu (`Sub`) zum Transformieren einer \<Beschreibung > Knoten in das angegebene HTML-Format. Diese Methode wird aufgerufen, durch den Code im vorherigen Schritt und wird verwendet, um das Format des beibehalten der \<Beschreibung > Elemente.  
  
     Diese Methode ersetzt die untergeordnete Elemente des der \<Description >-Element mit HTML. Die `ReplaceWith` Methode wird verwendet, um den Speicherort der untergeordneten Elemente beibehalten werden. Den transformierten Inhalt der \<Description >-Element in einer HTML-Abschnitt eingeschlossen wird (\<p >) Element. Die <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft wird verwendet, um den Inhalt des transformierten von Abrufen der \<Beschreibung > Element. Dadurch wird sichergestellt, dass untergeordnete Elemente in den transformierten Inhalt enthalten sind.  
  
     Fügen Sie den folgenden Code nach `Sub Main` von `Module1`.  
  
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
  
6. Drücken Sie F5, um den Code auszuführen. Das resultierende Dokument gespeichert werden wie folgt aussehen:  
  
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
  
## <a name="see-also"></a>Siehe auch

- [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)
- [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Vorgehensweise: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
