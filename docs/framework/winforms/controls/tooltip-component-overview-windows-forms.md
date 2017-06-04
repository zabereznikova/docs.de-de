---
title: "&#220;bersicht &#252;ber die ToolTip-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "ToolTip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolTip-Komponente [Windows Forms], Informationen über die ToolTip-Komponente"
  - "QuickInfo [Windows Forms], Informationen über QuickInfos"
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# &#220;bersicht &#252;ber die ToolTip-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.ToolTip>\-Komponente in Windows Forms zeigt Text an, wenn ein Benutzer auf Steuerelemente zeigt.  Jedem beliebigen Steuerelement kann eine QuickInfo zugeordnet werden.  Sie könnten diese Komponente z. B. verwenden, um Platz auf einem Formular zu sparen, indem Sie ein kleines Symbol auf einer Schaltfläche anzeigen und die Funktion der Schaltfläche mit einer QuickInfo erklären.  
  
## Arbeiten mit der ToolTip\-Komponente  
 Eine <xref:System.Windows.Forms.ToolTip>\-Komponente stellt mehreren Steuerelementen in einem Windows Form oder sonstigem Container eine `ToolTip`\-Eigenschaft bereit.  Wenn Sie z. B. eine <xref:System.Windows.Forms.ToolTip>\-Komponente auf einem Formular platzieren, können Sie den Text "Geben Sie Ihren Namen hier ein" für ein <xref:System.Windows.Forms.TextBox>\-Steuerelement und den Text "Klicken Sie hier, um Änderungen zu speichern" für ein <xref:System.Windows.Forms.Button>\-Steuerelement anzeigen lassen.  
  
 Die wichtigsten Methoden der <xref:System.Windows.Forms.ToolTip>\-Komponente sind <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> und <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.  Sie können die für die Steuerelemente angezeigten QuickInfos mit der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A>\-Methode festlegen.  Weitere Informationen finden Sie unter [Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).  Die wichtigsten Eigenschaften sind die <xref:System.Windows.Forms.ToolTip.Active%2A>\-Eigenschaft, die auf `true` festgelegt werden muss, damit die QuickInfo angezeigt wird, und die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>\-Eigenschaft, mit der festgelegt wird, wie lange die QuickInfo angezeigt wird, wie lange der Benutzer auf das Steuerelement zeigen muss, bis die QuickInfo angezeigt wird, und wie lange es dauert, bis die nächsten QuickInfo\-Fenster angezeigt werden.  Weitere Informationen finden Sie unter [Gewusst wie: Ändern der Verzögerung der ToolTip\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolTip>   
 [Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [Gewusst wie: Ändern der Verzögerung der ToolTip\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)