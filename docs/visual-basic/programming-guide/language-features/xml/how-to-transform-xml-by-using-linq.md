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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9f97466727064ea275c051b5916b0fb297e9e23a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Gewusst wie: Transformieren von XML unter Verwendung von LINQ (Visual Basic)
[XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) vereinfachen das XML aus einer Quelle gelesen und in ein neues XML-Format umgewandelt. Sie können Nutzen von LINQ-Abfragen zum Abrufen des Inhalts zu transformieren oder Ändern von Inhalt in einem vorhandenen Dokument in ein neues XML-Format.  
  
 Das Beispiel in diesem Thema transformiert Inhalt aus einem XML-Quelldokument in HTML in einem Browser angezeigt werden.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-transform-an-xml-document"></a>Um ein XML-Dokument zu transformieren.  
  
1.  Erstellen Sie in Visual Studio ein neues Visual Basic-Projekt in der **Konsolenanwendung** -Projektvorlage.  
  
2.  Doppelklicken Sie auf die Datei "Module1.vb" im Projekt so ändern Sie die Visual Basic-Code erstellt. Fügen Sie den folgenden Code der `Sub Main` von der `Module1` Modul. Dieser Code erstellt das XML-Quelldokument als ein <xref:System.Xml.Linq.XDocument>Objekt.</xref:System.Xml.Linq.XDocument>  
  
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
  
     [Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).  
  
3.  Nach dem Code zum Erstellen von XML-Quelldokument, fügen Sie den folgenden Code zum Abrufen von all den \<Buch > Elemente aus dem Objekt und deren Umwandlung in ein HTML-Dokument. Die Liste der \<Buch > Elemente wird mithilfe einer LINQ-Abfrage, die eine Auflistung von zurückgibt erstellt <xref:System.Xml.Linq.XElement>Objekte, die die transformierte HTML enthalten.</xref:System.Xml.Linq.XElement> Eingebettete Ausdrücke können Sie die Werte aus dem Quelldokument in das neue XML-Format eingefügt.  
  
     Die resultierende HTML-Dokument in eine Datei geschrieben wird, mithilfe der <xref:System.Xml.Linq.XElement.Save%2A>-Methode.</xref:System.Xml.Linq.XElement.Save%2A>  
  
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
  
4.  Nach `Sub Main` von `Module1`, fügen Sie eine neue Methode (`Sub`) zum Transformieren einer \<Beschreibung >-Knoten in das angegebene HTML-Format. Diese Methode wird aufgerufen, durch den Code im vorherigen Schritt, und wird verwendet, um das Format des beibehalten der \<Beschreibung > Elemente.  
  
     Diese Methode ersetzt die untergeordnete Elemente von der \<Beschreibung > Element durch HTML-Code. Die `ReplaceWith` -Methode verwendet, um die Position der Unterelemente zu erhalten. Den transformierten Inhalt von der \<Beschreibung > Element befindet sich auf einer HTML-Absatz (\<p >) Element. Die <xref:System.Xml.Linq.XContainer.Nodes%2A>Eigenschaft wird verwendet, um den transformierten Inhalt Abrufen der \<Beschreibung > Element.</xref:System.Xml.Linq.XContainer.Nodes%2A> Dadurch wird sichergestellt, dass Unterelemente im umgewandelten Inhalt enthalten sind.  
  
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
  
5.  Speichern Sie die Änderungen.  
  
6.  Drücken Sie F5, um den Code auszuführen. Das resultierende Dokument gespeichert wird folgendermaßen aussehen:  
  
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
 [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)

