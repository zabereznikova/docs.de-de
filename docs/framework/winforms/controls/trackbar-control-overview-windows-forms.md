---
title: "&#220;bersicht &#252;ber das TrackBar-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "TrackBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Schieberegler-Steuerelemente, Informationen über Schieberegler-Steuerelemente"
  - "Schieberegler, Informationen über Schieberegler"
  - "TrackBar-Steuerelement [Windows Forms], Informationen über das TrackBar-Steuerelement"
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# &#220;bersicht &#252;ber das TrackBar-Steuerelement (Windows&#160;Forms)
Mit dem <xref:System.Windows.Forms.TrackBar>\-Steuerelement in Windows Forms \(manchmal als auch "Schieberegler"\-Steuerelement bezeichnet\) können Sie durch große Datenmengen navigieren oder eine numerische Einstellung visuell anpassen.  Das <xref:System.Windows.Forms.TrackBar>\-Steuerelement besteht aus zwei Teilen: dem Ziehpunkt \(Schieberegler\) und den Teilstrichen.  Der Ziehpunkt ist der Teil, der angepasst werden kann.  Seine Position wird durch die <xref:System.Windows.Forms.TrackBar.Value%2A>\-Eigenschaft vorgegeben.  Die Teilstriche sind visuelle Zähler, die in regelmäßigen Abständen angeordnet sind.  Der Schieberegler der Positionsleiste wird in von Ihnen festgelegten Schrittweiten verschoben. Die Leiste kann horizontal oder vertikal ausgerichtet werden.  Mit der Trackleiste steuern Sie z. B. die Cursorblinkrate oder die Mausgeschwindigkeit eines Systems.  
  
## Haupteigenschaften  
 Die wichtigsten Eigenschaften des <xref:System.Windows.Forms.TrackBar>\-Steuerelements sind <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A> und <xref:System.Windows.Forms.TrackBar.Maximum%2A>.  <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> entspricht dem Abstand der Teilstriche.  <xref:System.Windows.Forms.TrackBar.Minimum%2A> und <xref:System.Windows.Forms.TrackBar.Maximum%2A> sind die niedrigsten und höchsten Werte, die auf der Trackleiste dargestellt werden können.  
  
 Zwei andere wichtige Eigenschaften sind <xref:System.Windows.Forms.TrackBar.SmallChange%2A> und <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.  Mit dem Wert der <xref:System.Windows.Forms.TrackBar.SmallChange%2A>\-Eigenschaft legen Sie die Anzahl der Positionen fest, um die ein Ziehpunkt bewegt wird, nachdem die NACH\-LINKS\- oder NACH\-RECHTS\-TASTE gedrückt wurde.  Der Wert der <xref:System.Windows.Forms.TrackBar.LargeChange%2A>\-Eigenschaft bestimmt die Anzahl der Positionen, um die der Ziehpunkt bewegt wird, nachdem die BILD\-AUF\- oder BILD\-AB\-TASTE gedrückt oder seitlich des Ziehpunkts auf die Trackleiste geklickt wurde.  
  
## Siehe auch  
 <xref:System.Windows.Forms.TrackBar>   
 [TrackBar\-Steuerelement](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)