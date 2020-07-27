---
title: 'Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements'
description: Erfahren Sie, wie Sie mit XAML ein TextBox-Steuerelement definieren, das erweitert wird, um mehrere Textzeilen in einer Windows Presentation Foundation Anwendung zu unterstützen.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166245"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements
In diesem Beispiel wird gezeigt, wie verwendet [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird, um ein Steuerelement zu definieren <xref:System.Windows.Controls.TextBox> , das automatisch erweitert wird, um mehrere Textzeilen anzupassen.  
  
## <a name="example"></a>Beispiel  
 Wenn das- <xref:System.Windows.Controls.TextBox.TextWrapping%2A> Attribut auf **Wrap** festgelegt wird, wird der eingegebene Text in eine neue Zeile eingeschlossen, wenn der Rand des <xref:System.Windows.Controls.TextBox> Steuer Elements erreicht wird. das Steuerelement wird automatisch erweitert, sodass es bei Bedarf den <xref:System.Windows.Controls.TextBox> Raum für eine neue Zeile einschließt.  
  
 Wenn das-Attribut auf "true" festgelegt <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> wird, wird eine neue Zeile eingefügt, wenn die Rückgabetaste gedrückt wird. wenn dies der **Fall** ist, wird das automatisch erweitert, <xref:System.Windows.Controls.TextBox> um Platz für eine neue Zeile einzuschließen.  
  
 Das- <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Attribut fügt der eine Bild Lauf Leiste hinzu <xref:System.Windows.Controls.TextBox> , sodass der Inhalt des <xref:System.Windows.Controls.TextBox> durchlaufen werden kann, wenn die <xref:System.Windows.Controls.TextBox> über die Größe des Frame oder Fensters hinausgeht, in dem Sie eingeschlossen wird.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.TextWrapping>
- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
