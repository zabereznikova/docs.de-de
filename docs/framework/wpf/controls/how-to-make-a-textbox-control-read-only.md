---
title: "Gewusst wie: Erstellen eines schreibgeschützten TextBox-Steuerelements"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 36116346b389dac7e9783e69d9bcd79573b4bf75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Gewusst wie: Erstellen eines schreibgeschützten TextBox-Steuerelements
In diesem Beispiel wird gezeigt, wie so konfigurieren Sie eine <xref:System.Windows.Controls.TextBox> Steuerelement, damit keine Benutzereingaben oder ändern können.  
  
## <a name="example"></a>Beispiel  
 Um zu verhindern, dass Benutzer ändern des Inhalts einer <xref:System.Windows.Controls.TextBox> steuern, legen Sie die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> -Attribut auf **"true"**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 Die <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> Attribut wirkt sich nur die Benutzereingabe; er hat keinen Einfluss auf Text festgelegt, der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beschreibung eine <xref:System.Windows.Controls.TextBox> Steuerelement oder Text programmgesteuert durch Festlegen der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft.  
  
 Der Standardwert von <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> ist **"false"**.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
