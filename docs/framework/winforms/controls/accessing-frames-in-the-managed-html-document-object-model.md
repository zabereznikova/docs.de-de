---
title: Zugreifen auf Frames im verwalteten HTML-Dokumentobjektmodell
ms.date: 03/30/2017
helpviewer_keywords:
- HTML [Windows Forms], dOM
- managed HTML DOM
- HTML [Windows Forms], managed
- HTML DOM [Windows Forms], managed
- frames [Windows Forms], accessing
- DOM [Windows Forms], accessing frames in managed HTML
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
ms.openlocfilehash: 9b2719ca000ab86b9ca40f9e78af46cbf598d16e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337629"
---
# <a name="accessing-frames-in-the-managed-html-document-object-model"></a>Zugreifen auf Frames im verwalteten HTML-Dokumentobjektmodell
Einige HTML-Dokumente bestehen aus *Frames*, oder Windows, die ihre eigenen HTML-Dokumente enthalten kann. Mit Frames ist es ganz einfach, HTML-Seiten zu erstellen, auf denen ein oder mehrere Teile statisch bleiben, wie die Navigationsleiste, während sich der Inhalt der anderen Frames permanent ändert.  
  
 HTML-Autoren können Frames in einer von zwei Weisen erstellen:  
  
-   Unter Verwendung der Tags `FRAMESET` und `FRAME`, womit feste Fenster erstellt werden,  
  
 - oder -   
  
-   mithilfe des Tags `IFRAME`, mit dem ein unverankertes Fenster erstellt wird, das zur Laufzeit neu positioniert werden kann.  
  
1. Da Frames HTML-Dokumente enthalten, werden sie im DOM (Document Object Model) sowohl als Fensterelemente als auch als Frameelemente dargestellt.  
  
2. Wenn Sie mit der Frames-Auflistung von <xref:System.Windows.Forms.HtmlWindow> auf ein `FRAME`- oder `IFRAME`-Tag zugreifen, rufen Sie ein Fensterelement ab, das dem Frame entspricht. Dies repräsentiert alle dynamischen Eigenschaften des Frames, wie die aktuelle URL, das Dokument und die Größe.  
  
3. Wenn Sie über die <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A>-Eigenschaft von <xref:System.Windows.Forms.HtmlWindow>, die <xref:System.Windows.Forms.HtmlElement.Children%2A>-Auflistung oder mit Methoden wie <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> oder <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> auf ein `FRAME`- oder `IFRAME`-Tag zugreifen, rufen Sie das Frameelement ab. Dies repräsentiert die statischen Eigenschaften des Frames, einschließlich der URL, die in der ursprünglichen HTML-Datei angegeben wurde.  
  
## <a name="frames-and-security"></a>Frames und Sicherheit  
 Zugriff auf Frames wird verkompliziert, durch die Tatsache, dass das verwaltete HTML-DOM eine Sicherheitsmaßnahme, bekannt als implementiert *frameübergreifenden skriptsicherheit*. Wenn ein Dokument ein `FRAMESET` mit zwei oder mehr `FRAME`s in unterschiedlichen Domänen enthält, können diese `FRAME`s nicht miteinander interagieren. Das heißt, eine `FRAME` , zeigt Inhalt von der Website nicht auf Informationen zugreifen kann eine `FRAME` , z. B. eine Drittanbieter-Website hostet `http://www.adatum.com/`. Diese Sicherheitsmaßnahme wird auf der Ebene der <xref:System.Windows.Forms.HtmlWindow>-Klasse implementiert. Sie können allgemeine Informationen zu einem `FRAME` abrufen, der Informationen von einer anderen Website hostet, wie dessen URL, sind aber nicht in der Lage, auf dessen <xref:System.Windows.Forms.HtmlWindow.Document%2A> zuzugreifen oder die Größe oder den Speicherort des Host-`FRAME`s oder -`IFRAME`s zu ändern.  
  
 Diese Regel gilt auch für Fenster, die sie mit den Methoden <xref:System.Windows.Forms.HtmlWindow.Open%2A> und <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A> öffnen. Wenn sich das von Ihnen geöffnete Fenster in einer anderen Domäne als die Seite befindet, die im <xref:System.Windows.Forms.WebBrowser>-Steuerelement gehostet wird, können Sie dieses Fenster nicht verschieben und dessen Inhalt nicht überprüfen. Diese Einschränkungen gelten auch, wenn Sie ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement zum Anzeigen einer Website verwenden, die sich von der Website unterscheidet, die zum Bereitstellen Ihrer Windows Forms-basierten Anwendung verwendet wird. Wenn Sie die [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Bereitstellungstechnologie zum Installieren Ihrer Website auf Website A und dann <xref:System.Windows.Forms.WebBrowser> zum Anzeigen von Website B verwenden, können Sie auf die Daten von Website B nicht zugreifen.  
  
## <a name="see-also"></a>Siehe auch

- [\<Frame >-Element](https://developer.mozilla.org/docs/Web/HTML/Element/frame)
- [Verwenden des verwalteten HTML-Dokumentobjektmodells](using-the-managed-html-document-object-model.md)
