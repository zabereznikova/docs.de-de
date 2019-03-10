---
title: 'Vorgehensweise: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: b9122e2c5bebdde2e04507973ccfeb924d0ad23e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723646"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>Vorgehensweise: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell
Die <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A>-Eigenschaft und die <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>-Steuerelements geben den HTML-Code des aktuellen Dokuments zurück, der bei der ersten Anzeige verwendet wurde. Wenn Sie jedoch die Seite mithilfe von Methoden- und Eigenschaftenaufrufen wie <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> und <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A> ändern, werden diese Änderungen nicht angezeigt, wenn Sie <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> und <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> aufrufen. Um die aktuelle HTML-Quelle für das DOM zu erhalten, müssen Sie die <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A>-Eigenschaft des HTML-Elements aufrufen.  
  
 Im folgenden Verfahren wird gezeigt, wie die dynamische Quelle abgerufen und in einem separaten Kontextmenü angezeigt wird.  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>Abrufen der dynamischen Quelle mit der OuterHtml-Eigenschaft  
  
1.  Erstellen Sie eine neue Windows Forms-Anwendung. Beginnen Sie mit einem einzelnen <xref:System.Windows.Forms.Form>, und nennen Sie sie `Form1`.  
  
2.  Host der <xref:System.Windows.Forms.WebBrowser> -Steuerelement in der Windows Forms-Anwendung, und nennen Sie sie `WebBrowser1`. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Erstellen Sie eine zweite <xref:System.Windows.Forms.Form> in Ihrer Anwendung namens `CodeForm`.  
  
4.  Hinzufügen einer <xref:System.Windows.Forms.RichTextBox> die Steuerung an `CodeForm` und legen Sie dessen <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft `Fill`.  
  
5.  Erstellen Sie eine öffentliche Eigenschaft auf `CodeForm` namens `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Hinzufügen einer <xref:System.Windows.Forms.Button> Steuerelement mit dem Namen `Button1` auf Ihre <xref:System.Windows.Forms.Form>, und überwachen Sie auf die <xref:System.Windows.Forms.Control.Click> Ereignis. Weitere Informationen zum Überwachen von Ereignissen finden Sie unter [Ereignisse](../../../standard/events/index.md).  
  
7.  Fügen Sie dem <xref:System.Windows.Forms.Control.Click>-Ereignishandler den folgenden Code hinzu.  
  
     [!code-csharp[DisplayWebBrowserCode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Testen Sie immer zuerst den Wert von <xref:System.Windows.Forms.WebBrowser.Document%2A>, bevor Sie einen Abruf versuchen. Wenn die aktuelle Seite noch nicht vollständig geladen wurde, kann <xref:System.Windows.Forms.WebBrowser.Document%2A> oder ein bzw. mehrere untergeordnete Objekte möglicherweise nicht initialisiert werden.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden des verwalteten HTML-Dokumentobjektmodells](using-the-managed-html-document-object-model.md)
- [Übersicht über das WebBrowser-Steuerelement](webbrowser-control-overview.md)
