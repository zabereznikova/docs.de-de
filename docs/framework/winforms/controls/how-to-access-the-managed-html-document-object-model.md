---
title: "Gewusst wie: Zugreifen auf das verwaltete HTML-Dokumentobjektmodell | Microsoft Docs"
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
  - "HTML-DOM zugreifen"
  - "verwaltete HTML-DOM zugreifen"
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Zugreifen auf das verwaltete HTML-Dokumentobjektmodell
Sie können auf das verwaltete HTML-Dokumentobjektmodell (DOM) von zwei Anwendungsarten aus zugreifen:  
  
-   Windows Forms-Anwendung (.exe), die die verwaltete gehostet <xref:System.Windows.Forms.WebBrowser> Steuerelement. Diese beiden Technologien ergänzen einander, mit der <xref:System.Windows.Forms.WebBrowser> Steuerelement der Seite für den Benutzer und das HTML-DOM, die logische Struktur des Dokuments darstellt.  
  
-   Windows Forms <xref:System.Windows.Forms.UserControl> in Internet Explorer gehostet. Sie können die Seite darstellt, die auf dem HTML-DOM zugreifen Ihre <xref:System.Windows.Forms.UserControl> gehostet wird, um die Struktur des Dokuments zu ändern oder modale Dialogfelder zu öffnen.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>So greifen Sie über eine Windows Forms-Anwendung auf das DOM zu  
  
1.  Host ein <xref:System.Windows.Forms.WebBrowser> innerhalb der Windows Forms-Anwendung steuern und überwachen Sie die <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Ereignis. Ausführliche Informationen über das Hosten von Steuerelementen und das Überwachen auf Ereignisse, finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md).  
  
2.  Abrufen der <xref:System.Windows.Forms.HtmlDocument> für die aktuelle Seite durch den Zugriff auf die <xref:System.Windows.Forms.WebBrowser.Document%2A> Eigenschaft der <xref:System.Windows.Forms.WebBrowser> Steuerelement.  
  
<!-- TODO: review snippet reference  [!CODE [AccessHTMLDOMApp#1](AccessHTMLDOMApp#1)]  -->  
  
### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>So greifen Sie von einem in Internet Explorer gehosteten UserControl auf das DOM zu  
  
1.  Erstellen Sie Ihre eigene benutzerdefinierte abgeleitete Klasse von der <xref:System.Windows.Forms.UserControl> Klasse. Weitere Informationen finden Sie unter [Gewusst wie: Erstellen zusammengesetzter Steuerelemente](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).  
  
2.  Platzieren Sie den folgenden Code innerhalb der Load-Ereignishandler für die <xref:System.Windows.Forms.UserControl>:  
  
 [!code-csharp[AccessHTMLDOMControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
1.  Wenn das DOM mithilfe der <xref:System.Windows.Forms.WebBrowser> -Steuerelement, sollten Sie immer warten, bis die <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Ereignis tritt auf, bevor Sie versuchen, Zugriff auf die <xref:System.Windows.Forms.WebBrowser.Document%2A> Eigenschaft der <xref:System.Windows.Forms.WebBrowser> Steuerelement. Die <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> -Ereignis wird ausgelöst, nachdem das gesamte Dokument geladen wurde, wenn Sie das DOM vorher verwenden, riskieren Sie, dass eine Laufzeitausnahme in der Anwendung.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
  
1.  Die Anwendung oder <xref:System.Windows.Forms.UserControl> setzen volle Vertrauenswürdigkeit voraus, um Zugriff auf das verwaltete HTML-DOM. Wenn Sie eine Windows Forms-Anwendung mit [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], können Sie die volle Vertrauenswürdigkeit ausweiten oder Bereitstellung einer vertrauenswürdigen Anwendung anfordern, finden Sie unter [Securing ClickOnce Applications](../Topic/Securing%20ClickOnce%20Applications.md) Details.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden des verwalteten HTML-Dokumentobjektmodells](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)