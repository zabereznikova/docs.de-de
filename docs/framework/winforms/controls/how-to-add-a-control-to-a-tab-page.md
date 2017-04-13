---
title: "Gewusst wie: Hinzuf&#252;gen eines Steuerelements zu einer Registerkarte | Microsoft Docs"
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
  - "Registerkarten-Steuerelemente, Aktivierreihenfolge"
  - "Registerkarten, Hinzufügen von Steuerelementen"
  - "TabPage-Steuerelement"
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Hinzuf&#252;gen eines Steuerelements zu einer Registerkarte
Sie können <xref:System.Windows.Forms.TabControl> in Windows Forms verwenden, um weitere Steuerelemente in einer strukturierten Weise anzuzeigen.  Das folgende Verfahren veranschaulicht, wie Sie der ersten Registerkarte eine Schaltfläche hinzufügen.  Informationen dazu, wie Sie dem Bezeichnungsteil einer Registerkarte ein Symbol hinzufügen, finden Sie unter [Gewusst wie: Ändern der Darstellung der TabControl\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### So fügen Sie ein Steuerelement programmgesteuert hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>\-Methode der Auflistung, die von der <xref:System.Windows.Forms.Control.Controls%2A>\-Eigenschaft von <xref:System.Windows.Forms.TabPage> zurückgegeben wird.  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## Siehe auch  
 [TabControl\-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [Übersicht über das TabControl\-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Gewusst wie: Ändern der Darstellung der TabControl\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)   
 [Gewusst wie: Deaktivieren von Registerkarten](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)