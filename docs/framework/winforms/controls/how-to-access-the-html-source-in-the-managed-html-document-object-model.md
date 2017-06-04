---
title: "Gewusst wie: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell | Microsoft Docs"
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
  - "HTML, Zugreifen auf in Windows Forms"
  - "Verwaltetes HTML-DOM"
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell
Die <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A>\-Eigenschaft und die <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>\-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>\-Steuerelements geben den HTML\-Code des aktuellen Dokuments zurück, der bei der ersten Anzeige verwendet wurde.  Wenn Sie jedoch die Seite mithilfe von Methoden\- und Eigenschaftenaufrufen wie <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> und <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A> ändern, werden diese Änderungen nicht angezeigt, wenn Sie <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> und <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> aufrufen.  Um die aktuelle HTML\-Quelle für das DOM zu erhalten, müssen Sie die <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A>\-Eigenschaft des HTML\-Elements aufrufen.  
  
 Im folgenden Verfahren wird gezeigt, wie die dynamische Quelle abgerufen und in einem separaten Kontextmenü angezeigt wird.  
  
### Abrufen der dynamischen Quelle mit der OuterHtml\-Eigenschaft  
  
1.  Erstellen Sie eine neue Windows Forms\-Anwendung.  Beginnen Sie mit einem einzelnen <xref:System.Windows.Forms.Form>, und nennen Sie es `Form1`.  
  
2.  Hosten Sie das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement in der Windows Forms\-Anwendung, und nennen Sie es `WebBrowser1`.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms\-Anwendung](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Erstellen Sie in der Anwendung ein zweites <xref:System.Windows.Forms.Form> mit dem Namen `CodeForm`.  
  
4.  Fügen Sie ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement zu `CodeForm` hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft auf `Fill` fest.  
  
5.  Erstellen Sie auf `CodeForm` eine öffentliche Eigenschaft mit dem Namen `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Fügen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement mit dem Namen `Button1` zum <xref:System.Windows.Forms.Form> hinzu, und überwachen Sie es auf das <xref:System.Windows.Forms.Control.Click>\-Ereignis.  Detaillierte Informationen zum Überwachen von Ereignissen finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md).  
  
7.  Fügen Sie dem <xref:System.Windows.Forms.Control.Click>\-Ereignishandler den folgenden Code hinzu.  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## Robuste Programmierung  
 Testen Sie immer zuerst den Wert von <xref:System.Windows.Forms.WebBrowser.Document%2A>, bevor Sie einen Abruf versuchen.  Wenn die aktuelle Seite noch nicht vollständig geladen wurde, kann <xref:System.Windows.Forms.WebBrowser.Document%2A> oder ein bzw. mehrere untergeordnete Objekte möglicherweise nicht initialisiert werden.  
  
## Siehe auch  
 [Verwenden des verwalteten HTML\-Dokumentobjektmodells](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)   
 [Übersicht über das WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)