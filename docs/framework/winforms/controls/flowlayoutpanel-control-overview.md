---
title: "&#220;bersicht &#252;ber das FlowLayoutPanel-Steuerelement | Microsoft Docs"
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
  - "FlowLayoutPanel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "FlowLayoutPanel-Steuerelement [Windows Forms], Informationen über das FlowLayoutPanel-Steuerelement"
  - "Formulare, Dynamisches Layout"
  - "Layout [Windows Forms], Dynamische"
  - "Windows Forms, Dynamisches Layout"
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber das FlowLayoutPanel-Steuerelement
Der Inhalt des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements wird in horizontaler oder vertikaler Flussrichtung angeordnet.  Dieser Inhalt kann von einer Zeile zur nächsten oder von einer Spalte zur nächsten umgebrochen werden.  Wahlweise können Sie den Inhalt auch abschneiden statt ihn umzubrechen.  
  
 Sie können die Flussrichtung angeben, indem Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>\-Eigenschaft festlegen.  Das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement kehrt seine Flussrichtung in Layouts mit Leserichtung von rechts nach links \(RTL\) entsprechend um.  Darüber hinaus können Sie angeben, ob der Inhalt des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements umgebrochen oder abgeschnitten wird, indem Sie den Wert der <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>\-Eigenschaft festlegen.  
  
 Das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement wird automatisch an seinen Inhalt angepasst, wenn Sie die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft auf `true` festlegen.  Zudem stellt es für seine untergeordneten Steuerelemente eine **FlowBreak**\-Eigenschaft bereit.  Wenn Sie den Wert der FlowBreak\-Eigenschaft auf `true` festlegen, ordnet das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement andere Steuerelemente nicht mehr in der aktuellen Flussrichtung an und bricht diese auch nicht mehr in die nächste Zeile oder Spalte um.  
  
 Jedes Windows Forms\-Steuerelement kann ein untergeordnetes Element des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements sein, einschließlich anderer Instanzen von <xref:System.Windows.Forms.FlowLayoutPanel>.  Dadurch sind Sie in der Lage, anspruchsvolle Layouts zu erstellen, die sich zur Laufzeit an die Maße des Formulars anpassen.  
  
 Siehe auch [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [FlowLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)