---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten TextBox-Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 7f24458eb98bd669d59f15c49d1d9e3beb6833b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229835"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Vorgehensweise: Erstellen eines schreibgeschützten TextBox-Steuerelements
Dieses Beispiel zeigt, wie Sie konfigurieren eine <xref:System.Windows.Controls.TextBox> Steuerelement, damit keine Benutzereingaben oder ändern können.  
  
## <a name="example"></a>Beispiel  
 Um zu verhindern, dass Benutzer ändern des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, legen Sie die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> -Attribut auf **"true"**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 Die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> Attribut wirkt sich auf nur die Benutzereingabe; er hat keine Auswirkungen auf Text, legen Sie in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beschreibung des eine <xref:System.Windows.Controls.TextBox> -Steuerelement oder Text programmgesteuert durch Festlegen der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft.  
  
 Der Standardwert von <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> ist **"false"**.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
