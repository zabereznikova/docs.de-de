---
title: 'Gewusst wie: Abrufen einer Textauswahl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32be79811de4b8056449c2c6d6c53eca8cc063f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-a-text-selection"></a>Gewusst wie: Abrufen einer Textauswahl
Dieses Beispiel zeigt eine Möglichkeit zum Verwenden der <xref:System.Windows.Controls.TextBox.SelectedText%2A> Eigenschaft, um Text abzurufen, die der Benutzer, in ausgewählt hat einem <xref:System.Windows.Controls.TextBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel zeigt die Definition eine <xref:System.Windows.Controls.TextBox> Steuerelement, das Text ausgewählt haben, enthält und eine <xref:System.Windows.Controls.Button> Steuerelement mit einem angegebenen <xref:System.Windows.Controls.Button.OnClick%2A> Methode.  
  
 In diesem Beispiel eine Schaltfläche mit einem zugeordneten <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler dient zum Abrufen der Textauswahl. Wenn der Benutzer die Schaltfläche klickt der <xref:System.Windows.Controls.Button.OnClick%2A> Methode alle markierten Text im Textfeld in eine Zeichenfolge kopiert. Die besonderen Umständen nach denen die Textauswahl abgerufen wird (Klicken auf eine Schaltfläche), sowie die Aktion, die mit dieser Auswahl (kopieren den markierten Text in eine Zeichenfolge), können problemlos geändert werden, um eine Vielzahl von Szenarien zu ermöglichen.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] Beispiel zeigt eine <xref:System.Windows.Controls.Button.OnClick%2A> -Ereignishandler für die Schaltfläche definiert, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für dieses Beispiel.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
