---
title: "How to: Enable XML IntelliSense in Visual Basic | Microsoft Docs"
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
  - "XML IntelliSense [Visual Basic]"
  - "XML [Visual Basic], IntelliSense"
  - "IntelliSense [Visual Basic], XML"
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# How to: Enable XML IntelliSense in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

IntelliSense für XML in Visual Basic stellt die Funktion der Wortvervollständigung für Elemente bereit, die in einem XML\-Schema definiert sind.  Führen Sie die folgenden Schritte aus, um IntelliSense für XML in Visual Basic zu aktivieren:  
  
1.  Rufen Sie die XML\-Schemadateien \(XSD\) für die XML\-Dateien ab, aus denen die Anwendung lesen oder in die sie schreiben soll.  
  
2.  Binden Sie die XML\-Schemadateien in das Projekt ein.  
  
3.  Importieren Sie die Zielnamespaces in die Codedatei oder das Projekt.  Ein Zielnamespace wird vom `targetNamespace`\-Attribut oder `tns`\-Attribut des XSD\-Schemas identifiziert.  
  
     Der Import eines Zielnamespaces kann entweder über die `Imports`\-Anweisung erfolgen, oder ein Namespace kann für alle Codedateien eines Projekt mithilfe der Seite **Verweise** des Projekt\-Designers hinzugefügt werden.  
  
 Weitere Informationen über die Funktionen von IntelliSense für XML in Visual Basic finden Sie unter [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  Weitere Informationen über das Importieren von XML\-Namespaces finden Sie unter [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) oder [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 [!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 ![Link zu Video](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Unter [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466) finden Sie eine Videodemonstration zu diesem Thema.  Eine ähnliche Videodemo finden Sie unter [How Do I Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).  
  
## Aktivieren von IntelliSense für XML in Visual Basic  
 Wenn Sie über eine XML\-Datei, jedoch nicht über die dazugehörige XSD\-Schemadatei verfügen, können Sie in SP1 mithilfe des XML\-zu\-Schema\-Assistenten eine XSD\-Schemadatei erstellen.  Darüber hinaus können Sie den Schemarückschluss im XML\-Editor von Visual Studio verwenden.  
  
#### So erstellen Sie eine XSD\-Schemadatei für eine XML\-Datei mithilfe eines XML\-zu\-Schema\-Assistenten \(SP1 erforderlich\)  
  
1.  Klicken Sie im Projekt im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
2.  Wählen Sie aus den Vorlagenkategorien **Daten** oder **Gemeinsame Elemente** die Elementvorlage **XML zu Schema** aus.  
  
3.  Geben Sie einen Namen für die XSD\-Datei\(en\) ein, in der\/denen das abgeleitete Schemaset gespeichert werden soll, und klicken Sie dann auf **Hinzufügen**.  
  
4.  Fügen Sie im Fenster **XML\-Schemaset aus XML\-Dokumenten ableiten** mindestens ein XML\-Dokument hinzu, aus dem das XML\-Schemaset abgeleitet werden soll.  
  
    -   So Textdateien hinzuzufügen, die XML\-Dokumente enthalten, indem Datei\-Explorer verwenden, auf **Aus Datei hinzufügen**.  
  
    -   Um ein XML\-Dokument aus einer HTTP\-Adresse hinzuzufügen, klicken Sie auf **Aus Web hinzufügen**.  
  
    -   Um Inhalte eines XML\-Dokuments in den Assistenten zu kopieren oder einzugeben, klicken Sie auf **XML eingeben oder einfügen**.  
  
5.  Wenn Sie alle XML\-Dokumentquellen angegeben haben, aus denen Sie das XML\-Schemaset ableiten möchten, klicken Sie zum Ableiten des XML\-Schemasets auf **OK**.  Das Schemaset wird im Projektordner in einer oder mehreren XSD\-Dateien gespeichert.  \(Es wird eine Datei für jeden XML\-Namespace im Schema erstellt.\)  
  
#### So erstellen Sie eine XSD\-Schemadatei für eine XML\-Datei mithilfe des Schemarückschlusses im XML\-Editor von Visual Studio  
  
1.  Bearbeiten Sie die XML\-Datei im XML\-Designer von Visual Studio.  
  
2.  Wenn sich der Cursor in der XML\-Datei befindet, wird das **XML**\-Menü angezeigt.  Klicken Sie im Menü **XML** auf **Schema erstellen**.  Eine XSD\-Datei wird aus dem von der XML\-Datei abgeleiteten XSD\-Schema erstellt.  
  
3.  Speichern Sie die XSD\-Schemadatei.  
  
    > [!NOTE]
    >  Es können verschiedene XSD\-Schemas von mehreren XML\-Dokumenten abgeleitet sein, die eigentlich über dasselbe Schema verfügen sollen.  Dies kann beispielsweise der Fall sein, wenn bestimmte Elemente und Attribute in einer XML\-Datei zu finden sind, in einer anderen jedoch nicht, oder wenn Elemente in verschiedenen Reihenfolgen enthalten sind.  Nach einem XSD\-Schemarückschluss sollten Sie die abgeleiteten XSD\-Schemas auf Vollständigkeit und Richtigkeit überprüfen.  
  
#### So binden Sie eine XSD\-Schemadatei ein  
  
-   In der Standardeinstellung werden XSD\-Dateien in Visual Basic\-Projekten nicht angezeigt.  Wenn sich die XSD\-Datei bereits in den Ordnern des Projekts befindet, klicken Sie im **Projektmappen\-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.  Suchen Sie die XSD\-Datei im **Projektmappen\-Explorer**, klicken Sie mit der rechten Maustaste auf die Datei, und klicken Sie auf **Datei in Projekt einschließen**.  
  
-   Wenn die XSD\-Datei noch nicht zum Projekt gehört, klicken Sie im **Projektmappen\-Explorer** auf den Ordner, in dem die XSD\-Datei gespeichert werden soll, zeigen auf **Hinzufügen** und klicken anschließend auf **Vorhandenes Element**.  Suchen Sie die XSD\-Datei, und klicken Sie auf **Hinzufügen**.  
  
#### So importieren Sie einen XML\-Namespace in eine Codedatei  
  
1.  Identifizieren Sie den Zielnamespace des XSD\-Schemas.  
  
2.  Fügen Sie am Anfang der Codedatei eine `Imports`\-Anweisung für den XML\-Zielnamespace hinzu, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]  
  
     Fügen Sie für den standardmäßigen XML\-Zielnamespace eine `Imports`\-Anweisung hinzu, um einen XML\-Namespace als Standardnamespace zu importieren. Dieser Namespace wird auf XML\-Elemente und \-Attribute angewendet, die über kein Namespacepräfix verfügen.  Geben Sie kein Namespacepräfix an.  Das folgende Beispiel zeigt eine `Imports`\-Anweisung.  
  
     [!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]  
  
#### So importieren Sie einen XML\-Namespace für alle Dateien in einem Projekt  
  
1.  Ein in eine Codedatei importierter XML\-Namespace gilt nur für diese Codedatei.  Zum Importieren eines für alle Codedateien in einem Projekt geltenden XML\-Namespaces öffnen Sie den Projekt\-Designer, indem Sie im **Projektmappen\-Explorer** auf **Mein Projekt** doppelklicken.  
  
2.  Geben Sie im Dialogfeld **Importierte Namespaces** auf der Registerkarte **Verweise** den XML\-Zielnamespace in Form einer vollständigen XML\-Namespacedeklaration ein \(z. B. `<xmlns: ns="http://sampleNamespace">`\).  Der Namespace wird zum standardmäßigen XML\-Namespace des Projekts, wenn vom XML\-Zielnamespace kein Namespacepräfix angegeben wird.  
  
3.  Klicken Sie auf **Benutzerimport hinzufügen**.  
  
## Siehe auch  
 [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)   
 [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)