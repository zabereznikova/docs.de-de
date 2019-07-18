---
title: 'Vorgehensweise: Aktivieren der Textverkürzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776126"
---
# <a name="how-to-enable-text-trimming"></a>Vorgehensweise: Aktivieren der Textverkürzung

Dieses Beispiel zeigt die Verwendung und die Werte zur Verfügung, in der <xref:System.Windows.TextTrimming> Enumeration.

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine <xref:System.Windows.Controls.TextBlock> -Element mit dem <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> -Attribut festgelegt.

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

Festlegen der entsprechenden <xref:System.Windows.TextTrimming> Eigenschaft im Code wird unten gezeigt.

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

Es gibt derzeit drei Optionen zum Verkürzen von Text aus: **CharacterEllipsis**, **WordEllipsis**, und **keine**.

Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> nastaven NA hodnotu **CharacterEllipsis**, Text gekürzt und mit einer Ellipse am nächsten Kante Zeichen fortgesetzt.  Diese Einstellung tendiert dazu, den Text zu kürzen, damit dieser besser an die Kürzungsgrenze passt. Dies kann jedoch dazu führen, dass Wörter teilweise abgeschnitten werden.  Die folgende Abbildung zeigt die Auswirkung dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> ähnlich der oben definierten.

![Anpassen von mit VSTU TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")

Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> nastaven NA hodnotu **WordEllipsis**, Text gekürzt und mit einer Ellipse am Ende des nächsten Kante ersten vollständigen Worts fortgesetzt.  Mit dieser Einstellung werden keine teilweise verkürzten Wörter angezeigt, aber meist nicht so weit zu Kante als Text zu kürzen der **CharacterEllipsis** festlegen.  Die folgende Abbildung zeigt die Auswirkung dieser Einstellung auf die <xref:System.Windows.Controls.TextBlock> oben definierten.

![Anpassen von mit VSTU TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")

Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> nastaven NA hodnotu **keine**, es wird keine textkürzung ausgeführt.  In diesem Fall wird Text einfach an der Begrenzung des übergeordneten Textcontainers zugeschnitten.  Die folgende Abbildung zeigt die Auswirkung dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> ähnlich der oben definierten.

![Anpassen von mit VSTU TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")
