---
title: "How to: Transform XML by Using LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML [Visual Basic], transforming"
  - "LINQ to XML [Visual Basic], transforming XML"
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Transform XML by Using LINQ (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Mit [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) kann XML leicht aus einer Quelle gelesen und in ein neues XML\-Format umgewandelt werden.  Sie können LINQ\-Abfragen nutzen, um den umzuwandelnden Inhalt abzurufen oder den Inhalt eines vorhandenen Dokuments in ein neues XML\-Format zu ändern.  
  
 Im Beispiel dieses Themas wird der Inhalt eines XML\-Quelldokuments in HTML umgewandelt, um ihn in einem Browser anzuzeigen.  
  
 [!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### So wandeln Sie ein XML\-Dokument um  
  
1.  Erstellen Sie in Visual Studio ein neues Visual Basic\-Projekt mit der Projektvorlage **Konsolenanwendung**.  
  
2.  Doppelklicken Sie auf die im Projekt erzeugte Datei Module1.vb, um den Visual Basic\-Code anzupassen.  Fügen Sie `Sub Main` des `Module1`\-Moduls folgenden Code hinzu.  Mit diesem Code wird das XML\-Quelldokument als <xref:System.Xml.Linq.XDocument>\-Objekt erzeugt.  
  
    ```vb#  
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
  
     [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).  
  
3.  Fügen Sie nach dem Code zur Erzeugung des XML\-Quelldokuments den folgenden Code hinzu, mit dem alle \<Book\>\-Elemente des Objekts abgerufen und in ein HTML\-Dokument umgewandelt werden.  Die Liste mit \<Book\>\-Elementen wird mit einer LINQ\-Abfrage erzeugt. Sie gibt eine Auflistung von <xref:System.Xml.Linq.XElement>\-Objekten zurück, die das umgewandelte HTML enthalten.  Mithilfe eingebetteter Ausdrücke können die Werte des Quelldokuments in das neue XML\-Format übertragen werden.  
  
     Das erzeugte HTML\-Dokument wird mit der <xref:System.Xml.Linq.XElement.Save%2A>\-Methode in eine Datei geschrieben.  
  
    ```vb#  
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
  
4.  Fügen Sie nach `Sub Main` von `Module1` eine neue Methode \(`Sub`\) hinzu, um einen \<Description\>\-Knoten in das angegebene HTML\-Format umzuwandeln.  Diese Methode wird vom Code des vorherigen Schritts aufgerufen und wird verwendet, um das Format der \<Description\>\-Elemente beizubehalten.  
  
     Diese Methode ersetzt Unterelemente des \<Description\>\-Elements durch HTML.  Die `ReplaceWith`\-Methode wird verwendet, um die Position der Unterelemente zu erhalten.  Der umgewandelte Inhalt des \<Description\>\-Elements wird in ein HTML\-Absatzelement \(\<p\>\) eingeschlossen.  Die <xref:System.Xml.Linq.XContainer.Nodes%2A>\-Eigenschaft wird verwendet, um den umgewandelten Inhalt des \<Description\>\-Elements abzurufen.  Damit wird sichergestellt, dass Unterelemente im umgewandelten Inhalt enthalten sind.  
  
     Fügen Sie nach `Sub Main` von `Module1` den folgenden Code ein.  
  
    ```vb#  
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
  
6.  Drücken Sie F5, um den Code auszuführen.  Das erzeugte und abgespeicherte Dokument sieht etwa folgendermaßen aus:  
  
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
  
## Siehe auch  
 [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)