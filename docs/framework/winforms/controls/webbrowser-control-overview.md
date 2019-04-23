---
title: Übersicht über das WebBrowser-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: c75d0b348a2f3dd678f2bfb235bce2e4e227c4b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109434"
---
# <a name="webbrowser-control-overview"></a>Übersicht über das WebBrowser-Steuerelement
Die <xref:System.Windows.Forms.WebBrowser> Steuerelement stellt einen verwalteten Wrapper für das WebBrowser ActiveX-Steuerelement. Der verwaltete Wrapper ermöglicht die Anzeige von Webseiten in Windows Forms-Clientanwendungen. Sie können die <xref:System.Windows.Forms.WebBrowser> Möglichkeit über das Internet Explorer Webbrowserfunktionalität in Ihre Anwendung oder an Sie duplizieren kann Standardfunktionalität von Internet Explorer deaktivieren und das Steuerelement als einfachen HTML-Dokument-Viewer. Sie können auch das Steuerelement dem Formular DHTML-basierter Benutzeroberflächenelemente hinzu, und blenden die Tatsache, die sie in gehostet werden die <xref:System.Windows.Forms.WebBrowser> Steuerelement. Dadurch können Sie nahtlos-Steuerelemente mit Windows Forms-Steuerelementen in einer einzigen Anwendung kombinieren.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Häufig verwendete Eigenschaften, Methoden und Ereignisse  
 Die <xref:System.Windows.Forms.WebBrowser> Steuerelement besitzt mehrere Eigenschaften, Methoden und Ereignisse, die Sie verwenden können, finden Sie in Internet Explorer Kontrollen zu implementieren. Beispielsweise können Sie die `Navigate` Methode, um eine Adressleiste, implementieren und die `GoBack`, `GoForward`, `Stop`, und `Refresh` Methoden, die Navigationsschaltflächen auf einer Symbolleiste implementiert. Können Sie behandeln die `Navigated` -Ereignisses zum Aktualisieren der-Adressleiste mit dem Wert des der `Url` Eigenschaft und die Titelleiste mit dem Wert von der `DocumentTitle` Eigenschaft.  
  
 Wenn Sie Ihre eigenen Seiteninhalt innerhalb Ihrer Anwendung erstellen möchten, legen Sie die `DocumentText` Eigenschaft. Wenn Sie mit der das HTML Document Object Model (DOM) vertraut sind, können Sie auch den Inhalt der aktuellen Webseite durch Bearbeiten der `Document` Eigenschaft. Sie können diese Eigenschaft speichern und Ändern von Dokumenten im Arbeitsspeicher abgelegt und das Navigieren zwischen Dateien.  
  
 Die `Document` Eigenschaft sorgt ebenfalls im Webseitenskriptcode aus Ihrem Clientanwendungscode implementierte Methoden aufrufen. Legen Sie den Code Ihrer Clientanwendung aus Ihrem Skriptcode, den Zugriff auf die `ObjectForScripting` Eigenschaft. Das Objekt, das Sie angeben, von Ihrem Skriptcode wie möglich die `window.external` Objekt.  
  
|Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A> -Eigenschaft|Ruft ein Objekt, das verwalteten Zugriff auf das HTML Document Object Model (DOM) der aktuellen Webseite bereitstellt.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> -Ereignis|Tritt auf, wenn eine Webseite auf das Laden abgeschlossen ist.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A> -Eigenschaft|Übernimmt oder bestimmt den HTML-Code als Inhalt der aktuellen Webseite.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> -Eigenschaft|Ruft den Titel der aktuellen Webseite ab.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A>-Methode|Wechselt zur vorherigen Seite im Verlauf.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A>-Methode|Wechselt zur nächsten Seite im Verlauf.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A>-Methode|Navigiert zur angegebenen URL.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating> -Ereignis|Tritt auf, vor dem Beginn der Navigation aktivieren die Aktion abgebrochen werden soll.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> -Eigenschaft|Übernimmt oder bestimmt ein Objekt, das Webseitenskriptcode für die Kommunikation mit Ihrer Anwendung verwenden können.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A>-Methode|Gibt die aktuelle Webseite.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A>-Methode|Lädt die aktuelle Webseite neu.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A>-Methode|Hält die aktuelle Navigation und beendet dynamische Seitenelemente wie z. B. Sounds und Animationen.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A> -Eigenschaft|Übernimmt oder bestimmt die URL der aktuellen Webseite. Durch Festlegen dieser Eigenschaft wird das Steuerelement an die neue URL navigiert.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>
- <xref:System.Windows.Forms.WebBrowserEncryptionLevel>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>
- <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>
- <xref:System.Windows.Forms.WebBrowserReadyState>
- <xref:System.Windows.Forms.WebBrowserRefreshOption>
- [Vorgehensweise: Navigieren Sie zu einer URL mit dem WebBrowser-Steuerelement](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Vorgehensweise: Drucken Sie mit einem WebBrowser-Steuerelement](how-to-print-with-a-webbrowser-control.md)
- [Vorgehensweise: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [Vorgehensweise: Erstellen Sie eine HTML-Dokumentviewers in einer Windows Forms-Anwendung](how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [Vorgehensweise: Implementieren der bidirektionalen Kommunikation zwischen DHTML-Code und Clientanwendungscode](implement-two-way-com-between-dhtml-and-client.md)
- [WebBrowser-Sicherheit](webbrowser-security.md)
