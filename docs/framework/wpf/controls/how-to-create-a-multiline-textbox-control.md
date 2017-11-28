---
title: 'Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 244eb38ea47bbd7376c2f8c6f5b2609fbd9c4330
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Gewusst wie: Erstellen eines mehrzeiligen TextBox-Steuerelements
Dieses Beispiel zeigt, wie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.TextBox> Steuerelement, das automatisch erweitert wird, um mehrere Textzeilen aufzunehmen.  
  
## <a name="example"></a>Beispiel  
 Festlegen der <xref:System.Windows.Controls.TextBox.TextWrapping%2A> -Attribut auf **umschließen** führt dazu, dass eingegebenen Text umbrochen, um eine neue Zeile am Rand des der <xref:System.Windows.Controls.TextBox> Steuerelement erreicht ist die <xref:System.Windows.Controls.TextBox> Steuerelement für eine neue Zeile aufzunehmen erforderlich.  
  
 Festlegen der <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> -Attribut auf **"true"** bewirkt, dass eine neue Zeile eingefügt, wenn die RETURN-Taste wieder automatisch zu erweitern gedrückt wird, die <xref:System.Windows.Controls.TextBox> Platz für eine neue Zeile bei Bedarf enthalten.  
  
 Die <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Attribut fügt eine Bildlaufleiste, um die <xref:System.Windows.Controls.TextBox>, sodass den Inhalt des der <xref:System.Windows.Controls.TextBox> Bildlauf durchgeführt werden kann, wenn die <xref:System.Windows.Controls.TextBox> erweitert die Größe des den Frame oder das Fenster, das es umschließt.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.TextWrapping>  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
