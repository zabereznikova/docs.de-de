---
title: 'Vorgehensweise: Anpassen des Abstands zwischen Absätzen'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777012"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Vorgehensweise: Anpassen des Abstands zwischen Absätzen
Dieses Beispiel zeigt, wie zum Anpassen oder Entfernen des Abstands zwischen Absätzen in fortlaufendem Inhalt.  
  
 In einem fortlaufenden Inhalt ist zusätzlichen Abstands zwischen Absätzen das Ergebnis der Ränder, legen Sie für diese Absätze; Daher kann der Abstand zwischen Absätzen gesteuert werden, durch Anpassen der Ränder auf den Absätzen.  Um einen zusätzlichen Abstand zwischen den beiden Absätze tauschen vollständig zu vermeiden, legen Sie die Ränder für die Absätze **0**.  Einheitliche Abstands zwischen Absätzen während einer gesamten erreichen <xref:System.Windows.Documents.FlowDocument>, verwenden Sie Formatierung, um für alle Absätze im ein einheitlicher Rand fest der <xref:System.Windows.Documents.FlowDocument>.  
  
 Es ist wichtig zu beachten, dass die Ränder für zwei angrenzende Absätze "reduzieren" werden der größere der beiden Ränder anstatt verdoppelt werden. Wenn zwei angrenzende Absätze bzw. Ränder 20 Pixel und 40 Pixel haben, ist der resultierende Abstand zwischen den Abschnitten also 40 Pixel, die größere der beiden Randwerte festgelegt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Formatierung auf den Rand für alle festzulegen <xref:System.Windows.Documents.Paragraph> Elemente in einem <xref:System.Windows.Documents.FlowDocument> zu **0**, wodurch effektiv entfällt zusätzlichen Abstand zwischen Absätzen in die <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
