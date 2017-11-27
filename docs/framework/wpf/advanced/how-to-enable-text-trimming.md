---
title: "Gewusst wie: Aktivieren der Textverkürzung"
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
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8f0f24bb6271e63dc50bd063aedfd8185711e7a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enable-text-trimming"></a>Gewusst wie: Aktivieren der Textverkürzung
Dieses Beispiel veranschaulicht die Verwendung und die Auswirkungen der Werte zur Verfügung, in der <xref:System.Windows.TextTrimming> Enumeration.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine <xref:System.Windows.Controls.TextBlock> Element mit dem <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> -Attribut festgelegt ist.  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a>Beispiel  
 Festlegen der entsprechenden <xref:System.Windows.TextTrimming> -Eigenschaft im Code wird unten veranschaulicht.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 Es gibt derzeit drei Optionen zum Verkürzen von Text: **CharacterEllipsis**, **WordEllipsis**, und **keine**.  
  
 Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> festgelegt ist, um **CharacterEllipsis**, Text gekürzt und mit einem Auslassungszeichen mit dem Zeichen, die dem Kürzen Rand am nächsten fortgesetzt.  Diese Einstellung tendiert dazu, den Text zu kürzen, damit dieser besser an die Kürzungsgrenze passt. Dies kann jedoch dazu führen, dass Wörter teilweise abgeschnitten werden.  Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> oben definierten ähnelt.  
  
 ![Beispiel: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")  
  
 Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> festgelegt ist, um **WordEllipsis**, Text gekürzt und mit einem Auslassungszeichen am Ende der ersten vollständigen Worts am nächsten an den Rand verkürzen fortgesetzt.  Diese Einstellung wird teilweise verkürzten Wörter nicht angezeigt, aber ist nicht so genau zu dem Kürzen Rand als Text Kürzen der **CharacterEllipsis** Einstellung.  Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf die <xref:System.Windows.Controls.TextBlock> oben definiert.  
  
 ![Beispiel: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")  
  
 Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> festgelegt ist, um **keine**, kein Text verkürzt wird ausgeführt.  In diesem Fall wird Text einfach an der Begrenzung des übergeordneten Textcontainers zugeschnitten.  Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> oben definierten ähnelt.  
  
 ![Beispiel: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")
