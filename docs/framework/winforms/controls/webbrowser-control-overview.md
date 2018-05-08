---
title: Übersicht über das WebBrowser-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 2e69b71b3e354101d950d6f7011b13fc7c0de030
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="webbrowser-control-overview"></a>Übersicht über das WebBrowser-Steuerelement
Die <xref:System.Windows.Forms.WebBrowser> Steuerelement stellt einen verwalteten Wrapper für das WebBrowser ActiveX-Steuerelement. Der verwaltete Wrapper können Sie die Anzeige von Webseiten in Windows Forms-Clientanwendungen. Sie können die <xref:System.Windows.Forms.WebBrowser> Steuerelement in Internet Explorer Webbrowserfunktionalität in Ihre Anwendung oder an Sie duplizieren Standardfunktionalität von Internet Explorer deaktivieren und das Steuerelement als einfache HTML-Dokument-Viewer verwenden kann. Sie können auch das Steuerelement dem Formular DHTML-basierter Elemente der Benutzeroberfläche hinzu, und blenden die Tatsache, dass die in dem sie gehostet werden die <xref:System.Windows.Forms.WebBrowser> Steuerelement. Dieser Ansatz können Sie nahtlos Websteuerelemente mit Windows Forms-Steuerelemente in einer einzigen Anwendung kombiniert.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Häufig verwendete Eigenschaften, Methoden und Ereignisse  
 Die <xref:System.Windows.Forms.WebBrowser> Steuerelement verfügt über verschiedene Eigenschaften, Methoden und Ereignisse, die Sie verwenden können, finden in Internet Explorer Kontrollen zu implementieren. Können z. B. die `Navigate` Methode, um eine Adressleiste implementieren und die `GoBack`, `GoForward`, `Stop`, und `Refresh` Methoden, die auf einer Symbolleiste Navigationsschaltflächen implementiert. Sie behandeln können die `Navigated` Ereignis beim Aktualisieren der Adressleiste mit dem Wert von der `Url` -Eigenschaft und die Titelleiste mit dem Wert von der `DocumentTitle` Eigenschaft.  
  
 Wenn Sie einen eigene Seiteninhalt innerhalb der Anwendung generieren möchten, legen Sie die `DocumentText` Eigenschaft. Wenn Sie mit der HTML-Dokumentobjektmodell (DOM) vertraut sind, können Sie auch den Inhalt der aktuellen Webseite durch Bearbeiten der `Document` Eigenschaft. Sie können diese Eigenschaft speichern und Ändern von Dokumenten im Arbeitsspeicher anstelle von Navigieren zwischen Dateien.  
  
 Die `Document` Eigenschaft auch, können Sie in der Webseite Skriptcode aus Ihrem Clientanwendungscode implementierte Methoden aufrufen. Legen Sie den Zugriff auf Ihrem Clientanwendungscode aus Ihrem Skriptcode, den `ObjectForScripting` Eigenschaft. Das Objekt, das Sie angeben, kann zugegriffen werden, durch den Skriptcode als das `window.external` Objekt.  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft|Ruft ein Objekt, das bietet verwalteten Zugriff auf das HTML-Dokumentobjektmodell (DOM) der aktuellen Webseite ab.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>-Ereignis|Tritt auf, wenn das Laden eine Webseite abgeschlossen ist.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A>-Eigenschaft|Abrufen oder Festlegen der Inhalt der aktuellen Webseite den HTML-Code.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>-Eigenschaft|Ruft den Titel der aktuellen Webseite ab.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A>-Methode|Wechselt zur vorherigen Seite im Verlauf.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A>-Methode|Navigiert zur nächsten Seite im Verlauf.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A>-Methode|Navigiert zur angegebenen URL.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating>-Ereignis|Tritt vor dem Beginn der Navigation Aktivieren der Aktion abgebrochen werden.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>-Eigenschaft|Ruft ab oder legt ein Objekt, das Webseitenskriptcode für die Kommunikation mit Ihrer Anwendung verwenden können.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A>-Methode|Druckt die aktuelle Webseite an.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A>-Methode|Lädt die aktuelle Webseite an.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A>-Methode|Hält die aktuelle Navigation und beendet dynamische Seitenelemente wie Sounds und Animation.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A>-Eigenschaft|Ruft ab oder legt die URL der aktuellen Webseite fest. Durch Festlegen dieser Eigenschaft wird das Steuerelement an die neue URL navigiert.|  
  
## <a name="see-also"></a>Siehe auch  
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
 [Gewusst wie: Navigieren zu einer URL mit dem WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [Gewusst wie: Drucken mit einem WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 [Gewusst wie: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 [Gewusst wie: Erstellen eines HTML-Dokumentviewers in einer Windows Forms-Anwendung](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 [Gewusst wie: Implementieren der bidirektionalen Kommunikation zwischen DHTML-Code und Clientanwendungscode](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 [WebBrowser-Sicherheit](../../../../docs/framework/winforms/controls/webbrowser-security.md)
