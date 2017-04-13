---
title: "Gewusst wie: Ausf&#252;hren von Drag&#160;&amp;&#160;Drop-Operationen zwischen Anwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Drag & Drop, Zwischen Anwendungen"
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Ausf&#252;hren von Drag&#160;&amp;&#160;Drop-Operationen zwischen Anwendungen
Das Ausführen von Drag & Drop\-Vorgängen zwischen Anwendungen unterscheidet sich nicht vom Aktivieren dieser Aktion innerhalb einer Anwendung, so lange sich die beiden betroffenen Anwendungen gemäß dem "Vertrag" verhalten, der zwischen den Eigenschaften <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> und <xref:System.Windows.Forms.DragEventArgs.Effect%2A> eingerichtet wurde.  
  
 Im folgenden Verfahren verwenden Sie eine von Ihnen erstellte Windows\-basierte Anwendung und das im Windows\-Betriebssystem enthaltene Textverarbeitungsprogramm WordPad, um Drag & Drop\-Vorgänge zwischen Anwendungen auszuführen.  WordPad verfügt über einen bestimmten Satz an zulässigen Effekte für Drag & Drop\-Text. Die Windows\-basierte Anwendung, für die Sie Code schreiben, arbeitet mit diesen Effekten, damit die Drag & Drop\-Vorgänge erfolgreich ausgeführt werden können.  
  
### So führen Sie ein Drag & Drop\-Verfahren zwischen Anwendungen aus  
  
1.  Erstellen Sie eine neue Windows Forms\-Anwendung.  
  
2.  Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TextBox>\-Steuerelement hinzu.  
  
3.  Konfigurieren Sie das <xref:System.Windows.Forms.TextBox>\-Steuerelement, um abgelegte Daten zu empfangen.  
  
     Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ausführen von Drag & Drop\-Operationen in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
4.  Führen Sie die Windows\-basierte Anwendung aus. Während die Anwendung aktiv ist, führen Sie WordPad aus.  
  
     WordPad ist ein Text\-Editor von Windows, der Drag & Drop\-Vorgänge ermöglicht.  Sie können auf WordPad zugreifen, indem Sie auf die Schaltfläche **Start** klicken, die Option **Ausführen** auswählen und anschließend `WordPad` in das Textfeld des Dialogfelds **Ausführen** eingeben. Abschließend klicken Sie auf **OK**.  
  
5.  Sobald WordPad geöffnet ist, geben Sie eine Textzeichenfolge ein.  
  
6.  Mit der Maus markieren Sie den Text, und ziehen Sie den markierten Text dann zum <xref:System.Windows.Forms.TextBox>\-Steuerelement in der Windows\-basierten Anwendung.  
  
     Wenn sich die Maus über dem <xref:System.Windows.Forms.TextBox>\-Steuerelement befindet \(und damit folglich das <xref:System.Windows.Forms.Control.DragEnter>\-Ereignis ausgelöst wird\), können Sie erkennen, dass sich der Cursor geändert hat. Sie können den markierten Text dann im <xref:System.Windows.Forms.TextBox>\-Steuerelement ablegen.  
  
     Darüber hinaus können Sie das <xref:System.Windows.Forms.TextBox>\-Steuerelement konfigurieren, damit Textzeichenfolgen per Drag & Drop in WordPad eingefügt werden können.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ausführen von Drag & Drop\-Operationen in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
## Siehe auch  
 [Gewusst wie: Hinzufügen von Daten zur Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [Gewusst wie: Abrufen von Daten aus der Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [Drag & Drop\-Operationen und Unterstützung der Zwischenablage](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)