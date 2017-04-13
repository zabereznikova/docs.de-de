---
title: "Gewusst wie: Erstellen eines HTML-Dokumentviewers in einer Windows Forms-Anwendung | Microsoft Docs"
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
  - "Dokument-Viewer"
  - "WebBrowser-Steuerelement [Windows Forms], Erstellen eines HTML-Dokument-Viewers"
  - "Windows Forms, Erstellen von Dokument-Viewern"
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen eines HTML-Dokumentviewers in einer Windows Forms-Anwendung
Mit dem <xref:System.Windows.Forms.WebBrowser>\-Steuerelement können Sie HTML\-Dokumente anzeigen und drucken, ohne die volle Funktionalität eines Internetwebbrowsers zur Verfügung zu stellen.  Das ist sinnvoll, wenn die Formatierungsfunktionen von HTML genutzt werden sollen, die Benutzer jedoch keine beliebigen Webseiten laden sollen, die möglicherweise nicht vertrauenswürdige Websteuerelemente oder bösartigen Skriptcode enthalten.  So können Sie beispielsweise die Funktionalität des <xref:System.Windows.Forms.WebBrowser>\-Steuerelements einschränken, wenn Sie dieses als HTML\-Viewer für E\-Mails oder zum Bereitstellen einer HTML\-Hilfe in Ihrer Anwendung verwenden möchten.  
  
### So erstellen Sie einen HTML\-Dokument\-Viewer  
  
1.  Legen Sie die <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>\-Eigenschaft auf `false` fest, damit Dateien, die auf das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement gezogen werden, nicht geöffnet werden.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  Legen Sie die <xref:System.Windows.Forms.WebBrowser.Url%2A>\-Eigenschaft auf den Speicherort der bei der Initialisierung anzuzeigenden Datei fest.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.WebBrowser>\-Steuerelement mit dem Namen `webBrowser1`.  
  
-   Verweise auf die `System`\-Assembly und die `System.Windows.Forms`\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>   
 <xref:System.Windows.Forms.WebBrowser.Url%2A>   
 [Übersicht über das WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [WebBrowser\-Sicherheit](../../../../docs/framework/winforms/controls/webbrowser-security.md)   
 [Gewusst wie: Navigieren zu einem URL mit dem WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [Gewusst wie: Drucken mit einem WebBrowser\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)