---
title: "&#220;bersicht &#252;ber das WebBrowser-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WebBrowser"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Webseiten, Anzeigen in Anwendungen"
  - "WebBrowser-Steuerelement [Windows Forms], Informationen über"
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# &#220;bersicht &#252;ber das WebBrowser-Steuerelement
Das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement stellt einen verwalteten Wrapper für das WebBrowser\-ActiveX\-Steuerelement bereit.  Mit dem verwalteten Wrapper können Sie Webseiten in Windows Forms\-Clientanwendungen anzeigen.  Mit dem <xref:System.Windows.Forms.WebBrowser>\-Steuerelement können Sie die Webbrowserfunktionalität von Internet Explorer in der Anwendung duplizieren oder die Standardfunktionalität von Internet Explorer deaktivieren und das Steuerelement als einfachen HTML\-Dokument\-Viewer verwenden.  Mit diesem Steuerelement können Sie außerdem einem Formular DHTML\-basierte Benutzerschnittstellenelemente hinzufügen und negieren, dass sie im <xref:System.Windows.Forms.WebBrowser>\-Steuerelement integriert sind.  Diese Vorgehensweise ermöglicht die reibungslose Kombination von Websteuerelementen und Windows Forms\-Steuerelementen in einer Anwendung.  
  
## Häufig verwendete Eigenschaften, Methoden und Ereignisse  
 Das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement verfügt über verschiedene Eigenschaften, Methoden und Ereignisse für die Implementierung von Internet Explorer\-Steuerelementen.  So können Sie z. B. mit der `Navigate`\-Methode eine Adressleiste implementieren, und mit den Methoden `GoBack`, `GoForward`, `Stop` und `Refresh` können Sie Navigationsschaltflächen in einer Symbolleiste implementieren.  Durch Behandlung des `Navigated`\-Ereignisses können Sie die Adressleiste mit dem Wert der `Url`\-Eigenschaft und die Titelleiste mit dem Wert der `DocumentTitle`\-Eigenschaft aktualisieren.  
  
 Wenn Sie in der Anwendung einen eigenen Seiteninhalt erstellen möchten, können Sie die `DocumentText`\-Eigenschaft festlegen.  Falls Sie mit dem HTML\-Dokumentenobjektmodell \(DOM\) vertraut sind, können Sie den Inhalt der aktuellen Webseite auch mit der `Document`\-Eigenschaft bearbeiten.  Mit dieser Eigenschaft können Sie Dokumente im Speicher ablegen und bearbeiten, anstatt zwischen Dateien zu navigieren.  
  
 Mit der `Document`\-Eigenschaft können Sie auch im Webseitenskriptcode implementierte Methoden von Ihrem Clientanwendungscode aus aufrufen.  Um mithilfe des Skriptcodes auf den Clientanwendungscode zuzugreifen, legen Sie die `ObjectForScripting`\-Eigenschaft fest.  Der Skriptcode kann auf das angegebene Objekt als `window.external`\-Objekt zugreifen.  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A>\-Eigenschaft|Ruft ein Objekt ab, das einen verwalteten Zugriff auf das HTML\-Dokumentenobjektmodell \(DOM\) der aktuellen Webseite ermöglicht.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>\-Ereignis|Tritt auf, wenn eine Webseite vollständig geladen ist.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A>\-Eigenschaft|Ruft den HTML\-Inhalt der aktuellen Webseite ab bzw. legt ihn fest.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>\-Eigenschaft|Ruft den Titel der aktuellen Webseite ab.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A>\-Methode|Navigiert im Navigationsverlauf zur vorherigen Seite.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A>\-Methode|Navigiert im Navigationsverlauf zur nächsten Seite.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A>\-Methode|Navigiert zur angegebenen URL.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating>\-Ereignis|Tritt vor dem Beginn der Navigation auf und ermöglicht den Abbruch der Aktion.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>\-Eigenschaft|Ruft ein Objekt ab bzw. legt es fest, das vom Webseitenskriptcode für die Kommunikation mit der Anwendung verwendet werden kann.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A>\-Methode|Druckt die aktuelle Webseite.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A>\-Methode|Lädt die aktuelle Webseite erneut.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A>\-Methode|Hält die aktuelle Navigation an und beendet dynamische Seitenelemente wie Sound und Animation.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A>\-Eigenschaft|Ruft die URL der aktuellen Webseite ab bzw. legt sie fest.  Mit der Festlegung dieser Eigenschaft wird das Steuerelement zur neuen URL navigiert.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>   
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>   
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>   
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>   
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>   
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserReadyState>   
 <xref:System.Windows.Forms.WebBrowserRefreshOption>   
 [Gewusst wie: Navigieren zu einem URL mit dem WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [Gewusst wie: Drucken mit einem WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)   
 [Gewusst wie: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms\-Anwendung](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)   
 [Gewusst wie: Erstellen eines HTML\-Dokumentviewers in einer Windows Forms\-Anwendung](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)   
 [Gewusst wie: Implementieren der bidirektionalen Kommunikation zwischen DHTML\-Code und Clientanwendungscode](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)   
 [WebBrowser\-Sicherheit](../../../../docs/framework/winforms/controls/webbrowser-security.md)