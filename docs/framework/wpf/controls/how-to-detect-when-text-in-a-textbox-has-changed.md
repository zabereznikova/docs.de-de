---
title: 'Vorgehensweise: Erkennen von Änderungen an Text in einem Textfeld'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 23bf0a88b3dc16491fbd520683385c65a58a7f6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696554"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Vorgehensweise: Erkennen von Änderungen an Text in einem Textfeld
Dieses Beispiel zeigt eine Möglichkeit zur Verwendung der <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis zum Ausführen einer Methode immer den Text in eine <xref:System.Windows.Controls.TextBox> -Steuerelements geändert hat.  
  
 In der CodeBehind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> -Steuerelement, das Sie überwachen möchten, Änderungen, fügen Sie eine Methode aufruft, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst wird.  Diese Methode müssen eine Signatur, die entspricht Erwartungen erfüllt werden die <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.  
  
 Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement geändert werden, entweder von einem Benutzer oder programmgesteuert.  
  
 **Hinweis**: Dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> -Steuerelement erstellt und erstmals mit Text aufgefüllt.  
  
## <a name="example"></a>Beispiel  
 In der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , definiert Ihr <xref:System.Windows.Controls.TextBox> geben die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Attribut mit einem Wert, der den Methodennamen des ereignishandlers übereinstimmt.  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a>Beispiel  
 In der CodeBehind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> -Steuerelement, das Sie überwachen möchten, Änderungen, fügen Sie eine Methode aufruft, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst wird.  Diese Methode müssen eine Signatur, die entspricht Erwartungen erfüllt werden die <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement geändert werden, entweder von einem Benutzer oder programmgesteuert.  
  
 **Hinweis**: Dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> -Steuerelement erstellt und erstmals mit Text aufgefüllt.  
  
 Kommentare  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
