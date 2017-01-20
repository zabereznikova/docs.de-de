---
title: "How to: Search Data in a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, implementing search"
  - "DataRepeater, searching data"
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Search Data in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement mit zahlreichen Datensätzen verwenden, können Sie den Benutzern ermöglichen, einen spezifischen Datensatz zu suchen.  Anstatt die Daten in dem Steuerelement selbst zu durchsuchen, können Sie eine Suche in Form einer Abfrage der zugrunde liegenden <xref:System.Windows.Forms.BindingSource> implementieren.  Wenn das Element gefunden wurde, können Sie es mit der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A>\-Eigenschaft auswählen und einblenden.  
  
### So implementieren Sie eine Suche  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TextBox>\-Steuerelement aus der **Toolbox** auf das Formular mit dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement.  
  
2.  Ändern Sie im Eigenschaftenfenster die **Name**\-Eigenschaft in SearchTextBox.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf das Formular mit dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement.  
  
4.  Ändern Sie im Eigenschaftenfenster die **Name**\-Eigenschaft in SearchButton.  Ändern Sie die **Text**\-Eigenschaft in Search.  
  
5.  Doppelklicken Sie auf das <xref:System.Windows.Forms.Button>\-Steuerelement, um den Code\-Editor zu öffnen, und fügen Sie dem `SearchButton_Click`\-Ereignishandler den folgenden Code hinzu.  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/VbPowerPacksDataRepeaterSearch/DataRepeaterSearch.vb#1)]
     [!code-cs[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/DataRepeaterSearchCS/DataRepeaterSearch.cs#1)]  
  
     Ersetzen Sie *ProductsBindingSource* durch den Namen der <xref:System.Windows.Forms.BindingSource> für <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und ersetzen Sie *ProductID* durch den Namen des Felds, das Sie durchsuchen möchten.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)