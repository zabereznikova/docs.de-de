---
title: "&#220;bersicht &#252;ber das LinkLabel-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "LinkLabel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Label-Steuerelement [Windows Forms], Informationen über das Label-Steuerelement"
  - "LinkLabel-Steuerelement [Windows Forms], Informationen über das LinkLabel-Steuerelement"
  - "Verknüpfungen, LinkLabel-Steuerelement"
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber das LinkLabel-Steuerelement (Windows&#160;Forms)
Mit dem <xref:System.Windows.Forms.LinkLabel>\-Steuerelement in Windows Forms können Sie Ihren Anwendungen für Windows Forms Webhyperlinks hinzufügen.  Grundsätzlich hat das <xref:System.Windows.Forms.LinkLabel>\-Steuerelement dieselben Funktionsmerkmale wie das <xref:System.Windows.Forms.Label>\-Steuerelement. Darüber hinaus können Sie damit einen Textteil als Link definieren, der auf eine Datei, einen Ordner oder eine Webseite verweist.  
  
## Mögliche Aktionen mit dem LinkLabel\-Steuerelement  
 Zusätzlich zu den Eigenschaften, Methoden und Ereignissen des <xref:System.Windows.Forms.Label>\-Steuerelements verfügt das <xref:System.Windows.Forms.LinkLabel>\-Steuerelement über Eigenschaften für Links und Linkfarben.  Mit der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Eigenschaft definieren Sie den Text, über den der Link aktiviert wird.  Die Eigenschaften <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> und <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> legen die Farben des Links fest.  Das <xref:System.Windows.Forms.LinkLabel.LinkClicked>\-Ereignis legt fest, welche Aktion erfolgt, nachdem der Linktext ausgewählt wurde.  
  
 Die einfachste Verwendungsmöglichkeit für das <xref:System.Windows.Forms.LinkLabel>\-Steuerelement ist die Anzeige eines einzelnen Links mit der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Eigenschaft. Jedoch können mit der <xref:System.Windows.Forms.LinkLabel.Links%2A>\-Eigenschaft auch mehrere Links angezeigt werden.  Mit der <xref:System.Windows.Forms.LinkLabel.Links%2A>\-Eigenschaft können Sie auf eine Auflistung von Links zugreifen.  Sie können auch Daten in der <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>\-Eigenschaft jedes einzelnen <xref:System.Windows.Forms.LinkLabel.Link>\-Objekts angeben.  Im Wert der <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>\-Eigenschaft lässt sich der Speicherort einer anzuzeigenden Datei oder die Adresse einer Website speichern.  
  
## Siehe auch  
 <xref:System.Windows.Forms.LinkLabel>   
 [Übersicht über das Label\-Steuerelement](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [Gewusst wie: Ändern der Darstellung des LinkLabel\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)