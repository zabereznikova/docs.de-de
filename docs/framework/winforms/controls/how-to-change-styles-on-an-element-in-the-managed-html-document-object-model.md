---
title: "Gewusst wie: &#196;ndern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Verwaltetes HTML-DOM, Ändern von Elementformaten"
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: &#196;ndern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell
Sie können mit Formaten in HTML die Darstellung eines Dokuments und seiner Elemente steuern.  <xref:System.Windows.Forms.HtmlDocument> und <xref:System.Windows.Forms.HtmlElement> unterstützen <xref:System.Windows.Forms.HtmlElement.Style%2A>\-Eigenschaften, die Formatzeichenfolgen im folgenden Format verwenden:  
  
 `name1:value1;...;nameN:valueN;`  
  
 Dies ist ein `DIV` mit einer Formatzeichenfolge, die die Schriftart auf Arial und den Text auf Fett festlegt:  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 Das Problem beim Bearbeiten von Formaten mithilfe der <xref:System.Windows.Forms.HtmlElement.Style%2A>\-Eigenschaft liegt darin, dass es umständlich sein kann, einzelne Formateinstellungen zur Zeichenfolge hinzuzufügen bzw. daraus zu entfernen.  Wenn beispielsweise der voranstehende Text kursiv angezeigt werden sollte, solange der Benutzer den Cursor über dem `DIV` positioniert, und normal, wenn er den Cursor vom `DIV` entfernt, würde dies zu einer komplexen Prozedur führen.  Es kann sehr zeitaufwändig sein, eine große Anzahl von Formaten auf diese Weise zu bearbeiten.  
  
 Die folgende Prozedur enthält Code, mit dem Sie Formate in HTML\-Dokumenten und \-Elementen leicht bearbeiten können.  Für diese Prozedur wird vorausgesetzt, dass Sie grundlegende Aufgaben in Windows Forms ausführen können, z. B. das Erstellen eines neuen Projekts oder das Hinzufügen eines Steuerelements zu einem Formular.  
  
### So verarbeiten Sie Formatänderungen in einer Windows Forms\-Anwendung  
  
1.  Erstellen Sie ein neues Projekt vom Typ Windows Forms.  
  
2.  Erstellen Sie eine neue Klassendatei, deren Erweiterung für Ihre Programmiersprache geeignet ist.  
  
3.  Kopieren Sie den `StyleGenerator`\-Klassencode im Beispielabschnitt dieses Themas in die Klassendatei, und speichern Sie den Code.  
  
4.  Speichern Sie den folgenden HTML\-Code in einer Datei mit dem Namen Test.htm.  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  Fügen Sie ein <xref:System.Windows.Forms.WebBrowser>\-Steuerelement mit dem Namen `webBrowser1` zum Hauptformular des Projekts hinzu.  
  
6.  Fügen Sie der Codedatei des Projekts folgenden Code hinzu.  
  
    > [!IMPORTANT]
    >  Stellen Sie sicher, dass der `webBrowser1_DocumentCompleted`\-Ereignishandler als Listener für das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>\-Ereignis konfiguriert ist.  Doppelklicken Sie in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] auf das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement. In einem Text\-Editor konfigurieren Sie den Listener programmgesteuert.  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  Führen Sie das Projekt aus.  Bewegen Sie den Cursor über dem ersten `DIV`, um die Auswirkungen des Codes zu überprüfen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird der vollständige Code für die `StyleGenerator`\-Klasse gezeigt, die einen vorhandenen Formatwert analysiert, das Hinzufügen, Ändern und Entfernen von Formaten unterstützt und einen neuen Formatwert mit den gewünschten Änderungen zurückgibt.  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.HtmlElement>