---
title: "Gewusst wie: Aktivieren der Textverk&#252;rzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dokumente, Verkürzen von Text"
  - "Text, Verkürzen"
  - "Verkürzen von Text"
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Aktivieren der Textverk&#252;rzung
In diesem Beispiel werden die Verwendung der Werte in der <xref:System.Windows.TextTrimming>\-Enumeration und ihre Auswirkungen veranschaulicht.  
  
## Beispiel  
 Das folgende Beispiel definiert ein <xref:System.Windows.Controls.TextBlock>\-Element mit dem <xref:System.Windows.Controls.TextBlock.TextTrimming%2A>\-Attributsatz.  
  
 [!code-xml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## Beispiel  
 Das Festlegen der entsprechenden <xref:System.Windows.TextTrimming>\-Eigenschaft in Code wird unten veranschaulicht.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 Es gibt derzeit drei Optionen zum Verkürzen von Text: **CharacterEllipsis**, **WordEllipsis** und **None**.  
  
 Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> auf **CharacterEllipsis** festgelegt ist, wird Text verkürzt und an dem Zeichen, das dem Rand für die Verkürzung am nächsten liegt, mit einer Ellipse fortgesetzt.  Bei dieser Einstellung besteht die Tendenz, dass Text für eine engere Anpassung an die Grenze für die Verkürzung abgeschnitten wird. Sie kann aber dazu führen, dass Wörter teilweise verkürzt werden.  Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock>, der dem oben definierten ähnelt.  
  
 ![Beispiel: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming\_Character")  
  
 Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> auf **WordEllipsis** festgelegt ist, wird Text verkürzt und am Ende des ersten vollständigen Worts, das dem Rand für die Verkürzung am nächsten liegt, mit einer Ellipse fortgesetzt.  Bei dieser Einstellung werden keine teilweise verkürzten Wörter angezeigt. Es besteht aber die Tendenz, dass Text, der sich so eng an der Grenze für die Verkürzung befindet wie bei der Einstellung **CharacterEllipsis**, nicht verkürzt wird.  Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf den oben definierten <xref:System.Windows.Controls.TextBlock> an.  
  
 ![Beispiel: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming\_Word")  
  
 Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> auf **None** festgelegt ist, wird Text nicht verkürzt.  In diesem Fall wird Text einfach an der Begrenzung des übergeordneten Textcontainers zugeschnitten.  Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock>, der dem oben definierten ähnelt.  
  
 ![Beispiel: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming\_None")