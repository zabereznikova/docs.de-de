---
title: 'Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld'
description: Erfahren Sie, wie Sie mit dem TextChanged-Ereignis eine Methode ausführen, wenn sich der Text in einem TextBox-Steuerelement in einer Windows Presentation Foundation Anwendung ändert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166221"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld

Dieses Beispiel zeigt eine Möglichkeit, mit dem- <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis eine Methode auszuführen, wenn sich der Text in einem- <xref:System.Windows.Controls.TextBox> Steuerelement geändert hat.

Fügen Sie in der Code Behind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , der das Steuerelement enthält, <xref:System.Windows.Controls.TextBox> das Sie auf Änderungen überwachen möchten, eine Methode ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> .  Diese Methode muss über eine Signatur verfügen, die mit dem, was vom Delegaten erwartet wird, übereinstimmt <xref:System.Windows.Controls.TextChangedEventHandler> .

Der Ereignishandler wird immer dann aufgerufen, wenn der Inhalt des <xref:System.Windows.Controls.TextBox> Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.

> [!NOTE]
> Dieses Ereignis wird ausgelöst, wenn das <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.

## <a name="example"></a>Beispiel

Geben Sie in der, die das [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Steuerelement definiert <xref:System.Windows.Controls.TextBox> , das- <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Attribut mit einem Wert an, der mit dem Namen der Ereignishandlermethode

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>Beispiel

Fügen Sie in der Code Behind-Klasse für den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , der das Steuerelement enthält, <xref:System.Windows.Controls.TextBox> das Sie auf Änderungen überwachen möchten, eine Methode ein, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> .  Diese Methode muss über eine Signatur verfügen, die mit dem, was vom Delegaten erwartet wird, übereinstimmt <xref:System.Windows.Controls.TextChangedEventHandler> .

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

Der Ereignishandler wird immer dann aufgerufen, wenn der Inhalt des <xref:System.Windows.Controls.TextBox> Steuer Elements geändert wird, entweder durch einen Benutzer oder Programm gesteuert.

> [!NOTE]
> Dieses Ereignis wird ausgelöst, wenn das <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und anfänglich mit Text aufgefüllt wird.

Kommentare

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
