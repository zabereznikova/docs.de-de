---
title: "Gewusst wie: Hinzufügen eines Wasserzeichens zu einer TextBox"
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
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92d619cb713e22d49e5c62bf7545d946b418dbda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Gewusst wie: Hinzufügen eines Wasserzeichens zu einer TextBox
Im folgende Beispiel wird gezeigt, wie die Verwendbarkeit einer <xref:System.Windows.Controls.TextBox> durch Anzeigen eines erläuternden Hintergrundbilds innerhalb eines der <xref:System.Windows.Controls.TextBox> bis der Benutzer Text eingibt, an welchem Punkt das Bild wird entfernt. Darüber hinaus wird das Hintergrundbild erneut wiederhergestellt werden, wenn der Benutzer die Eingabe entfernt. Siehe folgende Abbildung.  
  
 ![Ein Textfeld mit einem Hintergrundbild](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  Der Grund, ein Hintergrundbild wird in diesem Beispiel stattdessen dann einfach bearbeiten verwendet, die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft <xref:System.Windows.Controls.TextBox>, darin, dass ein Hintergrundbild nicht in Konflikt mit dem Datenbindung wird.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
