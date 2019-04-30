---
title: Zugreifen auf nicht verfügbar gemachte Member des verwalteten HTML-Dokumentobjektmodells
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 20341a44eb8a43a9d130e0b76d23b513738c6782
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011895"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Zugreifen auf nicht verfügbar gemachte Member des verwalteten HTML-Dokumentobjektmodells
Das verwaltete HTML (DOKUMENTOBJEKTMODELL) enthält eine Klasse namens <xref:System.Windows.Forms.HtmlElement> , verfügbar macht, die Eigenschaften, Methoden und Ereignisse, die alle HTML-Elemente gemeinsam haben. In einigen Fällen müssen Sie jedoch auf Member zuzugreifen, die die verwaltete Schnittstelle nicht direkt verfügbar gemacht wird. In diesem Thema werden zwei Methoden für den Zugriff auf nicht verfügbar gemachte Member, einschließlich untersucht [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] und VBScript-Funktionen, die innerhalb einer Webseite definiert.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Zugriff auf nicht verfügbar gemachte Member über verwaltete Schnittstellen  
 <xref:System.Windows.Forms.HtmlDocument> und <xref:System.Windows.Forms.HtmlElement> bieten vier Methoden, die Zugriff auf nicht verfügbar gemachte Member ermöglichen. Die folgende Tabelle zeigt die Typen und die entsprechenden Methoden.  
  
|Memberart|Methode(n)|  
|-----------------|-----------------|  
|Eigenschaften (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Methoden|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Ereignisse (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Ereignisse (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Ereignisse (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Wenn Sie diese Methoden verwenden, wird davon ausgegangen, dass Sie ein Element mit dem richtigen zugrunde liegenden Typ haben. Nehmen wir an, dass Sie überwachen möchten die `Submit` Ereignis eine `FORM` Element auf einer HTML-Seite, damit Sie eine vorverarbeitung für ausführen können die `FORM`Werte, bevor der Benutzer an den Server übermittelt. Im Idealfall, wenn Sie die Kontrolle über den HTML-Code haben, definieren Sie die `FORM` ein eindeutiges `ID` Attribut.  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 Laden Sie diese Seite in der <xref:System.Windows.Forms.WebBrowser> -Steuerelement, können Sie die <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> Methode zum Abrufen der `FORM` zur Laufzeit mit `form1` als Argument.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Zugreifen auf nicht verwalteten Schnittstellen  
 Sie können auch nicht verfügbar gemachte Member auf das verwaltete HTML-DOM zugreifen, mithilfe der nicht verwalteten Component Object Model (COM)-Schnittstellen, die von jeder DOM-Klasse verfügbar gemacht werden. Dies wird empfohlen, wenn Sie mehrere Aufrufe für nicht verfügbar gemachte Member erstellen müssen, oder die nicht verfügbar gemachte Member anderen nicht verwalteten Schnittstellen, die nicht von das verwaltete HTML-DOM. umschlossen zurückgibt  
  
 Die folgende Tabelle zeigt alle nicht verwalteten Schnittstellen verfügbar gemacht werden, über das verwaltete HTML-DOM. Klicken Sie auf jeden Link eine Erläuterung zur Verwendung sowie z. B. Code.  
  
|Typ|Nicht verwaltete Schnittstelle|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Die einfachste Möglichkeit, die COM-Schnittstellen zu verwenden ist, einen Verweis auf die nicht verwaltete HTML-DOM-Bibliothek (MSHTML.dll) von Ihrer Anwendung hinzufügen, obwohl dies nicht unterstützt wird. Weitere Informationen finden Sie unter [Knowledge Base-Artikel 934368](https://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Zugreifen auf die JavaScript-Funktionen  
 Eine HTML-Seite kann eine oder mehrere Funktionen definieren, indem Sie mithilfe einer Skriptsprache wie z. B. [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] oder VBScript. Diese Funktionen befinden sich in einem `SCRIPT` auf der Seite der Seite, und kann bei Bedarf oder in Reaktion auf ein Ereignis ausgeführt werden, im DOM.  
  
 Sie können alle Skriptfunktionen, die Sie definieren in einer HTML-Seite mit Aufrufen der <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> Methode. Wenn die Skriptmethode ein HTML-Elements zurückgibt, können eine Umwandlung konvertieren Sie dieses Ergebnis eine <xref:System.Windows.Forms.HtmlElement>. Ausführliche Informationen und Beispielcode finden Sie unter <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden des verwalteten HTML-Dokumentobjektmodells](using-the-managed-html-document-object-model.md)
