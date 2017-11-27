---
title: "Gewusst wie: Erstellen eines Steuerelements, das über eine Tastenkombination und Textumbruch verfügt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2a759011425a3f09a7b91b728442f8e8ea7b92fa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a>Gewusst wie: Erstellen eines Steuerelements, das über eine Tastenkombination und Textumbruch verfügt
Diese Beispiel veranschaulicht, wie Sie ein Steuerelement erstellen, das über eine Tastenkombination verfügt und das Umbrechen von Text unterstützt. Im Beispiel wird eine <xref:System.Windows.Controls.Label> Steuerelement zur Veranschaulichung dieser Konzepte.  
  
## <a name="example"></a>Beispiel  
 **Umbrechen des Texts einer Bezeichnung**  
  
 Die <xref:System.Windows.Controls.Label> Steuerelement unterstützt nicht den Textumbruch. Wenn sich eine Bezeichnung über mehrere Zeilen erstrecken soll, können Sie ein anderes Element verschachteln, das das Umbrechen von Text unterstützt, und es innerhalb der Bezeichnung platzieren. Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Controls.TextBlock> um eine Bezeichnung zu erstellen, die mehrere Textzeilen umschließt.  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **Hinzufügen von Textumbruch und einer Tastenkombination zu einer Bezeichnung**  
  
 Wenn die gewünschte eine <xref:System.Windows.Controls.Label> , hat es sich um eine Zugriffstaste (mnemonischen Codes), verwenden Sie die <xref:System.Windows.Controls.AccessText> Elements in der <xref:System.Windows.Controls.Label>.  
  
 Steuert, wie z. B. <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, und <xref:System.Windows.Controls.GroupBox> Steuerelementvorlagen Standardwert haben. Diese Vorlagen enthalten einen <xref:System.Windows.Controls.ContentPresenter>. Eine der Eigenschaften, die Sie auf festlegen, können die <xref:System.Windows.Controls.ContentPresenter> ist <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", damit können Sie eine Zugriffstaste für das Steuerelement festlegen.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Label> , die über eine Tastenkombination verfügt und Textumbruch unterstützt. So aktivieren Sie den Textumbruch, im Beispiel wird die <xref:System.Windows.Controls.AccessText.TextWrapping%2A> -Eigenschaft und verwendet ein Unterstrich-Zeichen zum Angeben des Zugriffsschlüssels. (Das Zeichen, das unmittelbar auf den Unterstrich folgt, ist die Tastenkombination.)  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Festlegen der Eigenschaft „Target“ einer Bezeichnung](http://msdn.microsoft.com/en-us/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
