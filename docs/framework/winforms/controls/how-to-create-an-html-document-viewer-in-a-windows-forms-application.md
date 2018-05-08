---
title: 'Gewusst wie: Erstellen eines HTML-Dokumentviewers in einer Windows Forms-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 1330e20cc4fe7df86e51bebca28e4a71e3108673
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Gewusst wie: Erstellen eines HTML-Dokumentviewers in einer Windows Forms-Anwendung
Sie können die <xref:System.Windows.Forms.WebBrowser> Steuerelement zum Anzeigen und Drucken von HTML-Dokumente ohne Angabe der vollständigen Funktionalität von einem Browser Internet. Dies ist hilfreich, wenn Sie die Formatierungsfunktionen von HTML nutzen möchten, aber nicht möchten, Ihre Benutzer, beliebige Webseiten zu laden, die möglicherweise nicht vertrauenswürdige Websteuerelemente oder potenziell bösartige Skriptcode enthalten. Möglicherweise möchten Sie die Funktionalität des Einschränken der <xref:System.Windows.Forms.WebBrowser> Steuern auf diese Weise z. B. auf, um ihn als eine HTML-e-Mail-Viewer verwenden oder HTML-Hilfe in der Anwendung bereitzustellen.  
  
### <a name="to-create-an-html-document-viewer"></a>So erstellen ein HTML-Dokument-viewer  
  
1.  Festlegen der <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> Eigenschaft, um `false` um zu verhindern, dass die <xref:System.Windows.Forms.WebBrowser> -Steuerelement aus, Öffnen von Dateien, die auf ihm abgelegt werden.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  Legen Sie die <xref:System.Windows.Forms.WebBrowser.Url%2A> Eigenschaft, um den Speicherort der ursprünglichen Datei angezeigt.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.  
  
-   Verweise auf die Assemblys `System` und `System.Windows.Forms`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [Übersicht über das WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser-Sicherheit](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [Gewusst wie: Navigieren zu einer URL mit dem WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [Gewusst wie: Drucken mit einem WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
