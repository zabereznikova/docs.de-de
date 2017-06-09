---
title: "&#220;bersicht &#252;ber das HScrollBar-Steuerelement und das VScrollBar-Steuerelement (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HScrollBar"
  - "VScrollBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "HScrollBar-Steuerelement [Windows Forms], Informationen über HScrollBar"
  - "Bildlaufleisten, Informationen über Bildlaufleisten"
  - "ScrollBar-Steuerelement [Windows Forms]"
  - "ScrollBar-Steuerelement [Windows Forms], Informationen über das ScrollBar-Steuerelement"
  - "VScrollBar-Steuerelement [Windows Forms], Informationen über das VScrollBar-Steuerelement"
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber das HScrollBar-Steuerelement und das VScrollBar-Steuerelement (Windows Forms)
<xref:System.Windows.Forms.ScrollBar>\-Steuerelemente von Windows Forms werden zur einfachen Navigation in einer langen Liste von Elementen oder einer großen Menge von Informationen mithilfe eines horizontalen bzw. vertikalen Bildlaufs in der Anwendung oder im Steuerelement eingesetzt.  Schiebeleisten sind ein häufig verwendetes Element der Windows\-Benutzeroberfläche. Daher wird das <xref:System.Windows.Forms.ScrollBar>\-Steuerelement häufig mit Steuerelementen verwendet, die nicht von der <xref:System.Windows.Forms.ScrollableControl>\-Klasse abgeleitet werden.  Außerdem beziehen viele Entwickler das <xref:System.Windows.Forms.ScrollBar>\-Steuerelement beim Erstellen eigener Benutzersteuerelemente mit ein.  
  
 Das <xref:System.Windows.Forms.HScrollBar>\-Steuerelement \(horizontal\) und das <xref:System.Windows.Forms.VScrollBar>\-Steuerelement \(vertikal\) funktionieren unabhängig von anderen Steuerelementen und verfügen über ihre eigenen Ereignisse, Eigenschaften und Methoden.  <xref:System.Windows.Forms.ScrollBar>\-Steuerelemente sind nicht mit den integrierten Bildlaufleisten identisch, die an Textfelder, Listenfelder, Kombinationsfelder oder MDI\-Formulare angehängt sind \(das <xref:System.Windows.Forms.TextBox>\-Steuerelement verfügt über eine <xref:System.Windows.Forms.TextBox.ScrollBars%2A>\-Eigenschaft zum Anzeigen oder Ausblenden von Bildlaufleisten, die an das Steuerelement angehängt sind\).  
  
 Die <xref:System.Windows.Forms.ScrollBar>\-Steuerelemente überwachen mithilfe des <xref:System.Windows.Forms.ScrollBar.Scroll>\-Ereignisses die Bewegungen des Bildlauffelds \(gelegentlich auch als Ziehpunkt bezeichnet\) auf der Schiebeleiste.  Die Verwendung des <xref:System.Windows.Forms.ScrollBar.Scroll>\-Ereignisses ermöglicht den Zugriff auf den Schiebeleistenwert während des Ziehvorgangs.  
  
## Werteigenschaft  
 Die <xref:System.Windows.Forms.ScrollBar.Value%2A>\-Eigenschaft \(deren Standardeinstellung 0 ist\) ist ein `integer`\-Wert, der der Position des Bildlauffelds auf der Schiebeleiste entspricht.  Wenn die Position des Bildlauffelds den kleinsten Wert aufweist, wird dieses an die äußerste linke Position \(bei horizontalen Schiebeleisten\) bzw. an die oberste Position \(bei vertikalen Schiebeleisten\) verschoben.  Wenn das Bildlauffeld den höchsten Wert aufweist, wird es an die äußerste rechte bzw. an die unterste Position verschoben.  Beim einem Wert in der Mitte zwischen der untersten und der obersten Position des Bereichs wird die Vorderkante des Bildlauffelds in der Mitte der Schiebeleiste platziert.  
  
 Der Benutzer kann den Schiebeleistenwert durch Mausklicks ändern oder das Bildlauffeld auch an einen beliebigen Punkt auf der Leiste ziehen.  Der resultierende Wert hängt von der Position des Bildlauffelds ab, liegt jedoch immer im Bereich zwischen der <xref:System.Windows.Forms.ScrollBar.Minimum%2A>\-Eigenschaft und der <xref:System.Windows.Forms.ScrollBar.Maximum%2A>\-Eigenschaft, die vom Benutzer festgelegt werden.  
  
## LargeChange\-Eigenschaft und SmallChange\-Eigenschaft  
 Wenn der Benutzer die BILD\-AUF\- oder die BILD\-AB\-TASTE drückt oder auf den Symbolleistenbereich neben bzw. oberhalb oder unterhalb des Bildlauffelds klickt, ändert sich die <xref:System.Windows.Forms.ScrollBar.Value%2A>\-Eigenschaft entsprechend dem in der <xref:System.Windows.Forms.ScrollBar.LargeChange%2A>\-Eigenschaft festgelegten Wert.  
  
 Wenn der Benutzer eine der Pfeiltasten drückt oder auf eine der Schaltflächen der Schiebeleiste klickt, ändert sich die <xref:System.Windows.Forms.ScrollBar.Value%2A>\-Eigenschaft entsprechend dem in der <xref:System.Windows.Forms.ScrollBar.SmallChange%2A>\-Eigenschaft festgelegten Wert.  
  
## Siehe auch  
 <xref:System.Windows.Forms.HScrollBar>   
 <xref:System.Windows.Forms.VScrollBar>   
 [Additions to Windows Forms for the .NET Framework 2.0](http://msdn.microsoft.com/de-de/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)