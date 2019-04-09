---
title: 'Vorgehensweise: Abrufen einer Textauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: b7f0b9ee02a7ace717787fc8eeb6e15649829a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224584"
---
# <a name="how-to-retrieve-a-text-selection"></a>Vorgehensweise: Abrufen einer Textauswahl
Dieses Beispiel zeigt eine Möglichkeit zur Verwendung der <xref:System.Windows.Controls.TextBox.SelectedText%2A> Eigenschaft, um Text abzurufen, die der Benutzer im ausgewählt verfügt über eine <xref:System.Windows.Controls.TextBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel zeigt die Definition von einer <xref:System.Windows.Controls.TextBox> -Steuerelement, das Text ausgewählt haben, enthält und eine <xref:System.Windows.Controls.Button> Steuerelement mit einem angegebenen <xref:System.Windows.Controls.Button.OnClick%2A> Methode.  
  
 In diesem Beispiel eine Schaltfläche mit einem zugeordneten <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler wird zum Abrufen der Textauswahl. Wenn der Benutzer auf die Schaltfläche klickt der <xref:System.Windows.Controls.Button.OnClick%2A> Methode kopiert die ausgewählten Text in das Textfeld in eine Zeichenfolge. Die jeweiligen Umstände, die von denen die Textauswahl abgerufen werden (Klicken auf eine Schaltfläche), sowie die Aktion, die mit dem die Auswahl (kopieren die Textauswahl in eine Zeichenfolge), kann problemlos geändert werden, um eine Vielzahl von Szenarien zu ermöglichen.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Beispiel  
 Die folgenden C# Beispiel zeigt eine <xref:System.Windows.Controls.Button.OnClick%2A> -Ereignishandler für die Schaltfläche definiert, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für dieses Beispiel.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
