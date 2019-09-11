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
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855623"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Vorgehensweise: Erkennen von Änderungen an Text in einem Textfeld

Dieses Beispiel zeigt eine Möglichkeit, mit dem <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis eine Methode auszuführen, wenn sich der Text <xref:System.Windows.Controls.TextBox> in einem-Steuerelement geändert hat.

Fügen Sie in der Code Behind-Klasse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für den, <xref:System.Windows.Controls.TextBox> der das Steuerelement enthält, das Sie auf Änderungen überwachen möchten, eine Methode <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird.  Diese Methode muss über eine Signatur verfügen, die mit dem <xref:System.Windows.Controls.TextChangedEventHandler> , was vom Delegaten erwartet wird, übereinstimmt.

Der Ereignishandler wird immer dann aufgerufen, wenn der <xref:System.Windows.Controls.TextBox> Inhalt des Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.

> [!NOTE]
> Dieses Ereignis wird ausgelöst, <xref:System.Windows.Controls.TextBox> wenn das Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.

## <a name="example"></a>Beispiel

Geben Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox> in der, die das Steuerelement <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> definiert, das-Attribut mit einem Wert an, der mit dem Namen der Ereignishandlermethode

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>Beispiel

Fügen Sie in der Code Behind-Klasse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für den, <xref:System.Windows.Controls.TextBox> der das Steuerelement enthält, das Sie auf Änderungen überwachen möchten, eine Methode <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird.  Diese Methode muss über eine Signatur verfügen, die mit dem <xref:System.Windows.Controls.TextChangedEventHandler> , was vom Delegaten erwartet wird, übereinstimmt.

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

Der Ereignishandler wird immer dann aufgerufen, wenn der <xref:System.Windows.Controls.TextBox> Inhalt des Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.

> [!NOTE]
> Dieses Ereignis wird ausgelöst, <xref:System.Windows.Controls.TextBox> wenn das Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.

Kommentare

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
