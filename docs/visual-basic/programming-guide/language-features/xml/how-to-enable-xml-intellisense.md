---
title: 'Gewusst wie: Aktivieren von XML IntelliSense in Visual Basic | Microsoft-Dokumentation'
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
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 84af19189fa3fc510c8d4f8e408cbb2a393d8b8f
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a>Gewusst wie: Aktivieren von IntelliSense für XML in Visual Basic
IntelliSense für XML in Visual Basic bietet wortvervollständigung für Elemente, die in einem XML-Schema definiert sind. Um IntelliSense für XML in Visual Basic zu aktivieren, müssen Sie Folgendes ausführen:  
  
1.  Rufen Sie die XML-Schemadatei (XSD) oder die Dateien für die XML-Dateien, die Ihre Anwendung lesen oder schreiben.  
  
2.  Schließen Sie die XML-Schemadateien in Ihr Projekt.  
  
3.  Importieren Sie den Zielnamespace oder Namespaces in die Codedatei oder das Projekt. Ein Zielnamespace wird anhand der `targetNamespace` oder `tns` -Attribut des XSD-Schemas.  
  
     Verwenden, um einen Zielnamespace Importieren der `Imports` -Anweisung, oder ein Namespace kann für alle Codedateien in einem Projekt hinzugefügt, mit der **Verweise** Seite im Projekt-Designer.  
  
 Weitere Informationen über die Funktionen von IntelliSense für XML in Visual Basic finden Sie unter [IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md). Weitere Informationen zum Importieren von XML-Namespaces finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) oder [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 ![Link zu Video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") eine Videoversion dieses Themas finden Sie unter [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466). Eine entsprechende Videodemo finden Sie unter [Gewusst wie: Aktivieren von XML IntelliSense und Verwenden von XML-Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a>Aktivieren von XML IntelliSense in Visual Basic  
 Wenn Sie eine XML-Datei verfügen, aber nicht über die XSD-Schemadatei verfügen, können in SP1 eine XSD-Schemadatei erstellen Sie mithilfe des XML-Schema-Assistenten. Sie können auch Schemarückschluss im XML-Editor von Visual Studio verwenden.  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a>Um eine XSD-Schemadatei für eine XML-Datei zu erstellen, mit dem XML-Schema-Assistenten erfordert (SP1)  
  
1.  Klicken Sie in Ihrem Projekt auf **neues Element hinzufügen** auf der **Projekt** Menü.  
  
2.  Wählen Sie die **Xml zu Schema** Elementvorlage entweder aus der **Daten** oder **gemeinsame Elemente** Kategorien.  
  
3.  Geben Sie einen Namen für die XSD-Dateien, die das abgeleitete Schemaset gespeichert werden soll, und klicken Sie dann auf **hinzufügen**.  
  
4.  In der **XML-Schemaset aus XML-Dokumenten ableiten** Fenster, fügen Sie eine oder mehrere XML-Dokumente um das XML-Schemaset aus.  
  
    -   Text-Dateien hinzufügen, die XML-Dokumente enthalten, mit dem Datei-Explorer, klicken Sie auf **aus Datei hinzufügen**.  
  
    -   Um ein XML-Dokument aus einer HTTP-Adresse hinzuzufügen, klicken Sie auf **aus Web hinzufügen**.  
  
    -   Zum Kopieren, oder geben Sie den Inhalt eines XML-Dokuments in den Assistenten, klicken Sie auf **XML eingeben oder einfügen**.  
  
5.  Wenn Sie angegeben haben, alle XML-Dokument-Quellen, die zum Ableiten des XML-Schemasets auf soll **OK** legen Sie die XML-Schema abgeleitet. Das Schemaset wird im Projektordner in einer oder mehreren XSD-Dateien gespeichert. (Für jeden XML-Namespace im Schema wird eine Datei erstellt.)  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a>So erstellen Sie eine XSD-Schemadatei für eine XML-Datei mit Schemarückschluss im XML-Editor von Visual Studio  
  
1.  Bearbeiten Sie die XML-Datei im XML-Designer von Visual Studio.  
  
2.  Wenn der Cursor an einer beliebigen Stelle in der XML-Datei, die **XML** Menü wird angezeigt. Klicken Sie auf **Create Schema** auf der **XML** Menü. Eine XSD-Datei wird aus der XML-Datei abgeleiteten XSD-Schema erstellt.  
  
3.  Speichern Sie die XSD-Schemadatei.  
  
    > [!NOTE]
    >  Verschiedene XSD-Schemas können aus mehreren XML-Dokumenten abgeleitet werden, die das gleiche Schema aufweisen sollen. Dies kann auftreten, wenn bestimmte Elemente und Attribute in einer XML-Datei und nicht in einem anderen gefunden werden, oder wenn Elemente in verschiedenen Reihenfolgen enthalten sind, z. B.. Sie sollten die abgeleiteten XSD-Schemas auf Vollständigkeit und Genauigkeit bei der Verwendung von XSD-Schemarückschluss überprüfen.  
  
#### <a name="to-include-an-xsd-schema-file"></a>Hinzufügen eine XSD-Schemadatei  
  
-   In der Standardeinstellung nicht XSD-Dateien in Visual Basic-Projekte angezeigt. Wenn die XSD-Datei bereits in den Ordnern für das Projekt enthalten ist, klicken Sie auf die **alle Dateien anzeigen** Schaltfläche **Projektmappen-Explorer**. Suchen Sie die XSD-Datei **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei, und klicken Sie auf **Datei in Projekt einschließen**.  
  
-   Ist die XSD-Datei nicht bereits Teil des Projekts, in **Projektmappen-Explorer**, mit der rechten Maustaste in des Ordners in dem Sie die XSD-Datei zu speichern, zeigen Sie auf möchten **hinzufügen**, und klicken Sie dann auf **vorhandenes Element**. Suchen Sie die XSD-Datei, und klicken Sie dann auf **hinzufügen**.  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a>So importieren Sie einen XML-Namespace in eine Codedatei.  
  
1.  Identifizieren Sie den Zielnamespace des XSD-Schemas.  
  
2.  Fügen Sie am Anfang der Codedatei eine `Imports` -Anweisung für den XML-Zielnamespace, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbXMLSamples&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]  
  
     Um ein XML-Namespace als Standardnamespace zu importieren, d. h. der Namespace, der angewendet wird, um XML-Elemente und Attribute, die nicht über ein Namespacepräfix verfügen Hinzufügen einer `Imports` -Anweisung für den standardmäßigen XML-Zielnamespace. Geben Sie ein Namespacepräfix. Es folgt ein Beispiel für eine `Imports` Anweisung.  
  
     [!code-vb[VbXmlSamples&#50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a>So importieren Sie einen XML-Namespace für alle Dateien in einem Projekt  
  
1.  Ein XML-Namespace importiert wird, in einer Codedatei gilt nur für diese Codedatei. Um ein XML-Namespace zu importieren, die für alle Codedateien in einem Projekt gilt, öffnen Sie den Projekt-Designer durch Doppelklicken auf **Mein Projekt** in **Projektmappen-Explorer**.  
  
2.  Auf der **Verweise** Registerkarte der **importierte Namespaces** Geben Sie den XML-Zielnamespace in Form einer vollständigen XML-Namespacedeklaration (z. B. `<xmlns: ns="http://sampleNamespace">`). Wenn Sie der XML-Zielnamespace kein Namespace-Präfix angegeben ist, wird der Namespace der XML-Standardnamespace für das Projekt sein.  
  
3.  Klicken Sie auf **Benutzerimport hinzufügen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)

