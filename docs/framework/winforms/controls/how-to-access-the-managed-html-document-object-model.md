---
title: 'Vorgehensweise: Zugreifen auf das verwaltete HTML-Dokumentobjektmodell'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 04d5f9e6f128d9b4ed3f07a5faebe06ae4ffdebf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315191"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a>Vorgehensweise: Zugreifen auf das verwaltete HTML-Dokumentobjektmodell
Sie können auf das verwaltete HTML-Dokumentobjektmodell (DOM) von zwei Anwendungsarten aus zugreifen:  
  
-   Eine Windows Forms-Anwendung (EXE), die das verwaltete <xref:System.Windows.Forms.WebBrowser>-Steuerelement gehostet hat. Diese beiden Technologien ergänzen sich gegenseitig, wobei das <xref:System.Windows.Forms.WebBrowser>-Steuerelement dem Benutzer die Seite anzeigt und das HTML-DOM die logische Struktur des Dokuments darstellt.  
  
-   Ein Windows Forms-<xref:System.Windows.Forms.UserControl>, das innerhalb von Internet Explorer gehostet wird. Sie können auf das HTML-DOM zugreifen, das die Seite darstellt, auf der das <xref:System.Windows.Forms.UserControl> gehostet wird, um beispielsweise unter anderem die Dokumentstruktur zu ändern oder modale Dialogfelder zu öffnen.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>So greifen Sie über eine Windows Forms-Anwendung auf das DOM zu  
  
1. Hosten Sie ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement innerhalb der Windows Forms-Anwendung, und überwachen Sie es auf das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>-Ereignis. Ausführliche Informationen über das Hosten von Steuerelementen und das Überwachen auf Ereignisse finden Sie unter [Ereignisse](../../../standard/events/index.md).  
  
2. Rufen Sie das <xref:System.Windows.Forms.HtmlDocument> für die aktuelle Seite ab, indem Sie auf die <xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>-Steuerelements zugreifen.  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>So greifen Sie von einem in Internet Explorer gehosteten UserControl auf das DOM zu  
  
1. Erstellen Sie Ihre eigene benutzerdefinierte abgeleitete Klasse der <xref:System.Windows.Forms.UserControl>-Klasse. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](how-to-author-composite-controls.md).  
  
2. Platzieren Sie den folgenden Code innerhalb des Load-Ereignishandlers für das <xref:System.Windows.Forms.UserControl>:  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
1. Wenn Sie das DOM mithilfe des <xref:System.Windows.Forms.WebBrowser>-Steuerelements verwenden, sollten Sie stets so lange warten, bis das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>-Ereignis auftritt, bevor Sie versuchen, auf die <xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>-Steuerelements zuzugreifen. Das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>-Ereignis wird ausgelöst, nachdem das gesamte Dokument geladen wurde. Wenn Sie das DOM vorher verwenden, besteht das Risiko, eine Laufzeitausnahme in der Anwendung zu verursachen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
  
1. Die Anwendung oder das <xref:System.Windows.Forms.UserControl> setzen volle Vertrauenswürdigkeit voraus, um auf das verwaltete HTML-DOM zuzugreifen. Wenn Sie eine Windows Forms-Anwendung mit [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] bereitstellen, können Sie volle Vertrauenswürdigkeit entweder über erweiterte Berechtigungen oder die Bereitstellung vertrauenswürdiger Anwendungen anfordern; ausführliche Informationen finden Sie unter [Sichern von ClickOnce-Anwendungen](/visualstudio/deployment/securing-clickonce-applications).  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden des verwalteten HTML-Dokumentobjektmodells](using-the-managed-html-document-object-model.md)
