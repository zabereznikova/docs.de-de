---
title: 'Vorgehensweise: Erstellen eines Steuerelements, das über eine Tastenkombination und Textumbruch verfügt'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 48e439719afa2426b5d8f822c621080cdc32514e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910922"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a>Vorgehensweise: Erstellen eines Steuerelements, das über eine Tastenkombination und Textumbruch verfügt
Diese Beispiel veranschaulicht, wie Sie ein Steuerelement erstellen, das über eine Tastenkombination verfügt und das Umbrechen von Text unterstützt. Im Beispiel wird eine <xref:System.Windows.Controls.Label> Steuerelement zur Veranschaulichung dieser Konzepte.  
  
## <a name="example"></a>Beispiel  
 **Umbrechen des Texts einer Bezeichnung**  
  
 Die <xref:System.Windows.Controls.Label> Umbrechen von Text-Steuerelement nicht unterstützt. Wenn sich eine Bezeichnung über mehrere Zeilen erstrecken soll, können Sie ein anderes Element verschachteln, das das Umbrechen von Text unterstützt, und es innerhalb der Bezeichnung platzieren. Das folgende Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Controls.TextBlock> um eine Bezeichnung zu erstellen, die mehrere Zeilen Text umbrochen wird.  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **Hinzufügen von Textumbruch und einer Tastenkombination zu einer Bezeichnung**  
  
 Bei Bedarf eine <xref:System.Windows.Controls.Label> , die über eine Tastenkombination (mnemonisches Zeichen) verfügt, verwenden Sie die <xref:System.Windows.Controls.AccessText> Elements in der <xref:System.Windows.Controls.Label>.  
  
 Steuert, wie z. B. <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, und <xref:System.Windows.Controls.GroupBox> haben Sie die Standard-Steuerelementvorlagen. Diese Vorlagen enthalten ein <xref:System.Windows.Controls.ContentPresenter>. Eine der Eigenschaften, die Sie auf festlegen, können die <xref:System.Windows.Controls.ContentPresenter> ist <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", damit können Sie eine Zugriffstaste für das Steuerelement an.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Label> , die über eine Tastenkombination verfügt und Umbrechen von Text unterstützt. So aktivieren Sie den Textumbruch, im Beispiel wird die <xref:System.Windows.Controls.AccessText.TextWrapping%2A> -Eigenschaft und verwendet ein Unterstrich-Zeichen um den Zugriffsschlüssel angeben. (Das Zeichen, das unmittelbar auf den Unterstrich folgt, ist die Tastenkombination.)  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Festlegen der Zieleigenschaft einer Bezeichnung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))
