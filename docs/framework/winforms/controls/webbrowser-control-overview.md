---
title: Übersicht über das WebBrowser-Steuerelement
description: Erfahren Sie, wie Sie mit dem Webbrowser-Steuerelement websteuer Elemente nahtlos mit Windows Forms-Steuerelementen in einer einzelnen Anwendung kombinieren.
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 6a0548bb0f5905d8f848ab13fb82d32b50caa891
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325739"
---
# <a name="webbrowser-control-overview"></a>Übersicht über das WebBrowser-Steuerelement
Das- <xref:System.Windows.Forms.WebBrowser> Steuerelement stellt einen verwalteten Wrapper für das WebBrowser-ActiveX-Steuerelement bereit. Mit dem verwalteten Wrapper können Sie Webseiten in Ihren Windows Forms Client Anwendungen anzeigen. Sie können das- <xref:System.Windows.Forms.WebBrowser> Steuerelement verwenden, um die Internet Explorer-Webbrowserfunktionen in Ihrer Anwendung zu duplizieren, oder Sie können die Standardfunktionalität von Internet Explorer deaktivieren und das-Steuerelement als einfachen HTML-Dokument- Sie können auch das-Steuerelement verwenden, um dem Formular DHTML-basierte Benutzeroberflächen Elemente hinzuzufügen und die Tatsache auszublenden, dass Sie im-Steuerelement gehostet werden <xref:System.Windows.Forms.WebBrowser> . Mit diesem Ansatz können Sie websteuer Elemente nahtlos mit Windows Forms-Steuerelementen in einer einzelnen Anwendung kombinieren.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Häufig verwendete Eigenschaften, Methoden und Ereignisse  
 Das <xref:System.Windows.Forms.WebBrowser> -Steuerelement verfügt über mehrere Eigenschaften, Methoden und Ereignisse, die Sie zum Implementieren von Steuerelementen verwenden können, die in Internet Explorer gefunden werden. Beispielsweise können Sie die `Navigate` -Methode verwenden, um eine Adressleiste zu implementieren, und die `GoBack` `GoForward` Methoden,, `Stop` und `Refresh` zum Implementieren von Navigations Schaltflächen auf einer Symbolleiste. Sie können das- `Navigated` Ereignis behandeln, um die Adressleiste mit dem Wert der `Url` -Eigenschaft und der Titelleiste mit dem Wert der-Eigenschaft zu aktualisieren `DocumentTitle` .  
  
 Wenn Sie Ihren eigenen Seiten Inhalt innerhalb Ihrer Anwendung generieren möchten, können Sie die- `DocumentText` Eigenschaft festlegen. Wenn Sie mit dem HTML-DOM (Document Object Model) vertraut sind, können Sie den Inhalt der aktuellen Webseite auch über die- `Document` Eigenschaft bearbeiten. Mit dieser Eigenschaft können Sie Dokumente im Arbeitsspeicher speichern und ändern, anstatt zwischen Dateien zu navigieren.  
  
 Mit der- `Document` Eigenschaft können Sie auch Methoden aufzurufen, die in Webseiten Skriptcode aus dem Client Anwendungscode implementiert werden. Legen Sie die-Eigenschaft fest, um über Ihren Skriptcode auf den Code der Client Anwendung zuzugreifen `ObjectForScripting` . Das Objekt, das Sie angeben, kann durch ihren Skriptcode als Objekt aufgerufen werden `window.external` .  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft|Ruft ein Objekt ab, das verwalteten Zugriff auf das HTML-DOM (Document Object Model) der aktuellen Webseite bereitstellt.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> -Ereignis|Tritt auf, wenn das Laden einer Webseite abgeschlossen ist.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A>-Eigenschaft|Ruft den HTML-Inhalt der aktuellen Webseite ab oder legt diesen fest.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>-Eigenschaft|Ruft den Titel der aktuellen Webseite ab.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A>-Methode|Navigiert zur vorherigen Seite im Verlauf.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A>-Methode|Navigiert zur nächsten Seite im Verlauf.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A>-Methode|Navigiert zur angegebenen URL.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating> -Ereignis|Tritt auf, bevor die Navigation beginnt, sodass die Aktion abgebrochen werden kann.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>-Eigenschaft|Ruft ein Objekt ab, mit dem Webseiten Skriptcode mit Ihrer Anwendung kommunizieren kann, oder legt dieses fest.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A>-Methode|Druckt die aktuelle Webseite.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A>-Methode|Lädt die aktuelle Webseite erneut.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A>-Methode|Stoppt die aktuelle Navigation und beendet dynamische Seitenelemente, wie z. b. Sounds und Animation.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A>-Eigenschaft|Ruft die URL der aktuellen Webseite ab oder legt Sie fest. Wenn Sie diese Eigenschaft festlegen, wird das-Steuerelement zur neuen URL navigiert.|  
  
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
- [Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Vorgehensweise: Drucken mit einem WebBrowser-Steuerelement](how-to-print-with-a-webbrowser-control.md)
- [Vorgehensweise: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [Vorgehensweise: Erstellen eines HTML-Dokumentviewers in einer Windows Forms-Anwendung](how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [Vorgehensweise: Implementieren der bidirektionalen Kommunikation zwischen DHTML-Code und Clientanwendungscode](implement-two-way-com-between-dhtml-and-client.md)
- [WebBrowser-Sicherheit](webbrowser-security.md)
