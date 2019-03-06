---
title: 'Vorgehensweise: Programmgesteuertes Einfügen eines Elements in Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: c93a1c7542a4ddb33b3880de423c256adcc3f1c3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378560"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a>Vorgehensweise: Programmgesteuertes Einfügen eines Elements in Text
Das folgende Beispiel zeigt, wie Sie mit zwei <xref:System.Windows.Documents.TextPointer> Objekte an einen Bereich innerhalb eines Texts Anwenden einer <xref:System.Windows.Documents.Span> Element.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel aussieht.  
  
 ![Ein auf einen Textbereich angewandtes SPAN-Element](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Flussdokumente](flow-document-overview.md)
