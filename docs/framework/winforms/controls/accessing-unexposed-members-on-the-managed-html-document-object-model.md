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
ms.openlocfilehash: d2fbccfb3ecd7716420ca951e86f728798d25258
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Zugreifen auf nicht verfügbar gemachte Member des verwalteten HTML-Dokumentobjektmodells
Das verwaltete HTML (DOKUMENTOBJEKTMODELL) enthält eine Klasse mit dem Namen <xref:System.Windows.Forms.HtmlElement> , verfügbar macht, die Eigenschaften, Methoden und Ereignisse, die alle HTML-Elemente gemeinsam haben. In einigen Fällen müssen Sie jedoch auf Member zuzugreifen, die nicht direkt von die verwaltete Schnittstelle verfügbar macht. In diesem Thema werden zwei Methoden für den Zugriff auf nicht verfügbar gemachte Member an, einschließlich untersucht [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] und VBScript-Funktionen, die innerhalb einer Webseite definiert.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Zugreifen auf nicht verfügbar gemachte Member über verwaltete Schnittstellen  
 <xref:System.Windows.Forms.HtmlDocument> und <xref:System.Windows.Forms.HtmlElement> vier Methoden bereit, die Zugriff auf nicht verfügbar gemachte Member ermöglichen. Die folgende Tabelle zeigt die Typen und die entsprechenden Methoden.  
  
|Memberart|Methode(n)|  
|-----------------|-----------------|  
|Eigenschaften (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Methoden|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Ereignisse (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Ereignisse (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Ereignisse (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Wenn Sie diese Methoden verwenden, wird davon ausgegangen, dass Sie ein Element mit dem richtigen zugrunde liegenden Typ aufweisen. Nehmen wir an, dass Sie überwachen möchten die `Submit` -Ereignis ein `FORM` Element auf einer HTML-Seite, sodass für einige erforderliche Verarbeitung ausgeführt werden können die `FORM`Werte, bevor die Benutzer an den Server gesendet. Im Idealfall, wenn Sie die Kontrolle über den HTML-Code haben, definieren Sie die `FORM` ein eindeutiges `ID` Attribut.  
  
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
  
 Nach dem Laden dieser Seite in der <xref:System.Windows.Forms.WebBrowser> -Steuerelement, können Sie die <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> Methode zum Abrufen der `FORM` zur Laufzeit mit `form1` als Argument.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Zugreifen auf nicht verwalteten Schnittstellen  
 Sie können auch nicht verfügbar gemachte Member auf das verwaltete HTML-DOM zugreifen, mithilfe der nicht verwalteten Component Object Model (COM)-Schnittstellen, die von jeder DOM-Klasse verfügbar gemacht werden. Dies wird empfohlen, wenn mehrere Aufrufe für nicht verfügbar gemachte Member vorgenommen werden muss oder nicht verfügbar gemachte Member andere nicht verwaltete Schnittstellen, die nicht vom verwalteten HTML DOM. umschlossen zurückgeben  
  
 Die folgende Tabelle zeigt alle nicht verwalteten Schnittstellen, die über das verwaltete HTML-DOM. verfügbar gemacht werden Klicken Sie auf jeden Link eine Erläuterung zur Verwendung sowie z. B. Code.  
  
|Typ|Nicht verwaltete Schnittstelle|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Die einfachste Möglichkeit zum Verwenden von COM-Schnittstellen ist einen Verweis auf die nicht verwaltete Bibliothek von HTML-DOM (MSHTML.dll) von Ihrer Anwendung hinzufügen, obwohl dies nicht unterstützt wird. Weitere Informationen finden Sie unter [Knowledge Base-Artikel 934368](http://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Zugreifen auf Skriptfunktionen  
 Eine HTML-Seite kann eine oder mehrere Funktionen definieren, indem Sie z. B. mithilfe einer Skriptsprache [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] oder VBScript. Diese Funktionen befinden sich innerhalb von einer `SCRIPT` auf der Seite der Seite ", und kann bei Bedarf oder als Reaktion auf ein Ereignis ausgeführt werden, auf das DOM validiert werden.  
  
 Sie können alle Skriptfunktionen, die Sie definieren in einer HTML-Seite mit Aufrufen der <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> Methode. Wenn Skriptmethode ein HTML-Element zurückgibt, können Sie eine Umwandlung verwenden, um dieses Ergebnis zu konvertieren einer <xref:System.Windows.Forms.HtmlElement>. Ausführliche Informationen und Beispielcode finden Sie unter <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden des verwalteten HTML-Dokumentobjektmodells](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
