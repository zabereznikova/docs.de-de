---
title: "Zugreifen auf nicht verf&#252;gbar gemachte Member des verwalteten HTML-Dokumentobjektmodells | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Verwaltetes HTML-DOM, Zugreifen auf nicht verfügbar gemachte Member"
  - "Nicht verfügbar gemachte Member"
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Zugreifen auf nicht verf&#252;gbar gemachte Member des verwalteten HTML-Dokumentobjektmodells
Das verwaltete HTML\-Dokumentobjektmodell \(DOM\) enthält eine Klasse mit dem Namen <xref:System.Windows.Forms.HtmlElement>, die die Eigenschaften, Methoden und Ereignisse verfügbar macht, die alle HTML\-Elemente gemeinsam haben.  Gelegentlich müssen Sie jedoch auf Member zugreifen, die die verwaltete Schnittstelle nicht direkt verfügbar macht.  In diesem Thema werden zwei Methoden zum Zugreifen auf nicht verfügbar gemachte Member untersucht, einschließlich [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)]\-Funktionen und VBScript\-Funktionen, die innerhalb einer Webseite definiert sind.  
  
## Zugreifen auf nicht verfügbar gemachte Member über verwaltete Schnittstellen  
 <xref:System.Windows.Forms.HtmlDocument> und <xref:System.Windows.Forms.HtmlElement> stellen vier Methoden bereit, die den Zugriff auf nicht verfügbar gemachte Member ermöglichen.  In der folgenden Tabelle werden die verschiedenen Arten und ihre entsprechenden Methoden angezeigt.  
  
|Memberart|Methode\(n\)|  
|---------------|------------------|  
|Eigenschaften \(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Methoden|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Ereignisse \(<xref:System.Windows.Forms.HtmlDocument>\)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Ereignisse \(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Ereignisse \(<xref:System.Windows.Forms.HtmlWindow>\)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Wenn Sie diese Methoden verwenden, wird davon ausgegangen, dass Sie über ein Element des richtigen zugrunde liegenden Typs verfügen.  Angenommen, Sie möchten das `Submit`\-Ereignis eines `FORM`\-Elements auf einer HTML\-Seite überwachen, sodass Sie die `FORM`\-Werte teilweise vorab verarbeiten können, bevor der Benutzer sie an den Server übermittelt.  Wenn Sie im Idealfall die Kontrolle über die HTML\-Seite haben, würden Sie für das `FORM` ein eindeutiges `ID`\-Attribut definieren.  
  
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
  
 Nachdem Sie diese Seite in das <xref:System.Windows.Forms.WebBrowser>\-Steuerelement geladen haben, können Sie die <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>\-Methode verwenden, um das `FORM` zur Laufzeit mithilfe des Arguments `form1` abzurufen.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## Zugreifen auf nicht verwaltete Schnittstellen  
 Sie können auch auf nicht verfügbar gemachte Member des verwalteten HTML\-DOM zugreifen, indem Sie die nicht verwalteten Schnittstellen des Komponentenobjektmodells \(COM\) verwenden, die von jeder DOM\-Klasse verfügbar gemacht werden.  Dies empfiehlt sich, wenn Sie mehrere Aufrufe für nicht verfügbar gemachte Member machen müssen oder wenn die nicht verfügbar gemachten Member andere nicht verwaltete Schnittstellen zurückgeben, die nicht vom verwalteten HTML\-DOM umschlossen sind.  
  
 Die folgende Tabelle zeigt alle nicht verwalteten Schnittstellen, die über das verwaltete HTML\-DOM verfügbar gemacht werden.  Klicken Sie auf die einzelnen Links, um eine Erklärung zur Verwendung sowie Beispielcode anzuzeigen.  
  
|type|Nicht verwaltete Schnittstelle|  
|----------|------------------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Die einfachste Methode, die COM\-Schnittstellen zu verwenden, besteht darin, einen Verweis auf die nicht verwaltete Bibliothek HTML\-DOM \(MSHTML.dll\) von der Anwendung hinzugefügt werden soll, auch wenn diese nicht unterstützt wird.  Weitere Informationen finden Sie [Knowledge Base\-Artikel 934368](http://support.microsoft.com/kb/934368)unter.  
  
## Zugreifen auf Skriptfunktionen  
 Eine HTML\-Seite kann mithilfe einer Skriptsprache wie [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] oder VBScript eine oder mehrere Funktionen definieren.  Diese Funktionen werden in eine `SCRIPT`\-Seite der Seite eingefügt und können bei Bedarf oder als Reaktion auf ein Ereignis im DOM ausgeführt werden.  
  
 Sie können alle Skriptfunktionen aufrufen, die Sie mit der <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>\-Methode in einer HTML\-Seite definieren.  Wenn die Skriptmethode ein HTML\-Element zurückgibt, können Sie dieses Ergebnis in ein <xref:System.Windows.Forms.HtmlElement> umwandeln.  Ausführliche Informationen und Beispielcode finden Sie unter <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## Siehe auch  
 [Verwenden des verwalteten HTML\-Dokumentobjektmodells](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)