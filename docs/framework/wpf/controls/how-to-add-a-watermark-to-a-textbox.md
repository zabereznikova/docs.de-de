---
title: 'Vorgehensweise: Hinzufügen eines Wasserzeichens zu einem TextBox-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923578"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Vorgehensweise: Hinzufügen eines Wasserzeichens zu einem TextBox-Objekt
Im folgenden Beispiel wird gezeigt, wie Sie die Verwendbarkeit eines <xref:System.Windows.Controls.TextBox> unterstützen können, indem Sie ein erklärendes Hintergrundbild innerhalb <xref:System.Windows.Controls.TextBox> von anzeigen, bis der Benutzer Text eingibt. an diesem Punkt wird das Bild entfernt. Außerdem wird das Hintergrundbild wieder hergestellt, wenn der Benutzer seine Eingabe entfernt. Siehe Abbildung unten.  
  
 ![Ein Textfeld mit einem Hintergrundbild](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
> Der Grund, warum ein Hintergrundbild in diesem Beispiel verwendet wird, anstatt einfach <xref:System.Windows.Controls.TextBox.Text%2A> die- <xref:System.Windows.Controls.TextBox>Eigenschaft von zu bearbeiten, besteht darin, dass ein Hintergrundbild die Datenbindung nicht beeinträchtigt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
