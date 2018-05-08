---
title: 'Gewusst wie: Anpassen des Abstands zwischen Absätzen'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: b232903054cf45b70ba99a9223352391498cf79b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Gewusst wie: Anpassen des Abstands zwischen Absätzen
Dieses Beispiel zeigt, wie anpassen oder Abstände zwischen den Absätzen in fortlaufendem Inhalt zunichte gemacht werden.  
  
 In fortlaufendem Inhalt ist zusätzlicher Speicherplatz, der zwischen Absätzen angezeigt wird das Ergebnis der Ränder auf diese Absätze festgelegt; Daher kann der Abstand zwischen den Absätzen durch Anpassen der Ränder auf diesen Absätzen gesteuert werden.  Um einen zusätzlichen Abstand zwischen zwei Absätzen vollständig zu vermeiden, legen Sie die Seitenränder für die Absätze **0**.  Einheitliche Abstand zwischen den Absätzen in der gesamten eine gesamte erzielen <xref:System.Windows.Documents.FlowDocument>, mithilfe der Formatvorlage fest einen uniform Margin-Wert für alle Absätze in der <xref:System.Windows.Documents.FlowDocument>.  
  
 Es ist wichtig zu beachten, dass die Ränder von zwei angrenzenden Absätzen "reduzieren" werden die größere von zwei Ränder anstatt verdoppelt werden. Wenn also zwei angrenzende Absätze Ränder eines 20 Pixel und 40 Pixel aufweisen, der sich ergebenden Abstand zwischen den Absätzen 40 Pixel, das größere der beiden Randwerte festgelegt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird formatieren, legen Sie den Rand für alle <xref:System.Windows.Documents.Paragraph> Elemente in einer <xref:System.Windows.Documents.FlowDocument> auf **0**, wodurch effektiv einen zusätzlichen Abstand zwischen den Absätzen in entfällt die <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
