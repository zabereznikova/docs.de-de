---
title: "Gewusst wie: Erstellen eines Steuerelements, das &#252;ber eine Tastenkombination und Textumbruch verf&#252;gt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zugriffstasten, Steuerelement für"
  - "Steuerelemente, Zugriffstasten"
  - "Steuerelemente, Umbrechen von Text"
  - "Schlüssel, Steuerelement für"
  - "Umbrechen von Text"
  - "Umbrechen von Text"
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Erstellen eines Steuerelements, das &#252;ber eine Tastenkombination und Textumbruch verf&#252;gt
In diesem Beispiel wird gezeigt, wie ein Steuerelement erstellt wird, das über eine [Tastenkombination](GTMT) verfügt und Textumbruch unterstützt.  Im Beispiel wird zur Veranschaulichung dieser Konzepte ein <xref:System.Windows.Controls.Label>\-Steuerelement verwendet.  
  
## Beispiel  
 **Hinzufügen von Textumbruch zur Bezeichnung**  
  
 Das <xref:System.Windows.Controls.Label>\-Steuerelement unterstützt keinen Textumbruch.  Wenn Sie eine Bezeichnung benötigen, die auf mehrere Zeilen aufgeteilt werden soll, können Sie ein anderes Element verschachteln, das Textumbruch unterstützt, und dieses Element innerhalb der Bezeichnung stellen.  Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.TextBlock> verwendet werden kann, um eine Bezeichnung zu erstellen, die auf mehrere Textzeilen aufgeteilt ist.  
  
 [!code-xml[Label#5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#5)]
 [!code-xml[Label#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#5)]  
  
 **Hinzufügen von Tastenkombination und Textumbruch zur Bezeichnung**  
  
 Wenn Sie eine <xref:System.Windows.Controls.Label> benötigen, der eine Tastenkombination \(Tastenkürzel\) zugeordnet ist, verwenden Sie das <xref:System.Windows.Controls.AccessText>\-Element, das sich innerhalb der <xref:System.Windows.Controls.Label> befindet.  
  
 Steuerelemente wie <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander> und <xref:System.Windows.Controls.GroupBox> haben Standardvorlagen für Steuerelemente.  Diese Vorlagen enthalten einen <xref:System.Windows.Controls.ContentPresenter>.  Eine der Eigenschaften, die Sie im <xref:System.Windows.Controls.ContentPresenter> festlegen können, ist <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>\="true". Diese Eigenschaft können Sie verwenden, um eine Tastenkombination für das Steuerelement anzugeben.  
  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Controls.Label> erstellt wird, die über eine Tastenkombination verfügt und Textumbruch unterstützt.  Um den Textumbruch zu aktivieren, legt das Beispiel die <xref:System.Windows.Controls.AccessText.TextWrapping%2A>\-Eigenschaft fest. Ein Unterstrichzeichen wird verwendet, um die Tastenkombination anzugeben.  \(Das Zeichen, das unmittelbar auf das Unterstrichzeichen folgt, ist die Tastenkombination.\)  
  
 [!code-xml[Label#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#4)]
 [!code-xml[Label#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#4)]  
  
## Siehe auch  
 [How to: Set the Target Property of a Label](http://msdn.microsoft.com/de-de/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)