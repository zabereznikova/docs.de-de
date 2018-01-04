---
title: "Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld"
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
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ef1da879026d8cbefd6ef1baeb6c315e0ea1c02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Gewusst wie: Erkennen von Änderungen an Text in einem Textfeld
Dieses Beispiel zeigt eine Möglichkeit zum Verwenden der <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Ereignis zur Ausführung einer Methode immer den Text in einem <xref:System.Windows.Controls.TextBox> -Steuerelements geändert hat.  
  
 In der CodeBehind-Klasse für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> Steuerelement, das Sie überwachen möchten, damit die Änderungen, fügen Sie eine Methode aufrufen, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst.  Diese Methode benötigen eine Signatur, die von entspricht dem <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.  
  
 Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement verwendet werden, von einem Benutzer oder programmgesteuert geändert.  
  
 **Hinweis:** dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und erstmals mit Text aufgefüllt.  
  
## <a name="example"></a>Beispiel  
 In der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , definiert die <xref:System.Windows.Controls.TextBox> geben die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Attribut mit einem Wert, der den Namen Ereignishandlermethode entspricht.  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a>Beispiel  
 In der CodeBehind-Klasse für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthält die <xref:System.Windows.Controls.TextBox> Steuerelement, das Sie überwachen möchten, damit die Änderungen, fügen Sie eine Methode aufrufen, wenn die <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> -Ereignis ausgelöst.  Diese Methode benötigen eine Signatur, die von entspricht dem <xref:System.Windows.Controls.TextChangedEventHandler> delegieren.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 Der Ereignishandler wird aufgerufen, wenn der Inhalt des der <xref:System.Windows.Controls.TextBox> Steuerelement verwendet werden, von einem Benutzer oder programmgesteuert geändert.  
  
 **Hinweis:** dieses Ereignis wird ausgelöst, wenn die <xref:System.Windows.Controls.TextBox> Steuerelement erstellt und erstmals mit Text aufgefüllt.  
  
 Kommentare  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
