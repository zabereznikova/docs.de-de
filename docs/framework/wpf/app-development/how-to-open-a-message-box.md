---
title: 'Vorgehensweise: Öffnen Sie ein Meldungsfeld'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: dd79d69c9b1b54c5158b58ee2f1675e7d11a386a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-open-a-message-box"></a>Vorgehensweise: Öffnen Sie ein Meldungsfeld
In diesem Beispiel wird gezeigt, wie ein Meldungsfeld geöffnet wird.  
  
## <a name="example"></a>Beispiel  
 Ein Meldungsfeld wird eine vorgefertigte modales Dialogfeld zum Anzeigen von Informationen für Benutzer. Ein Meldungsfeld geöffnet wird, durch Aufrufen der statischen <xref:System.Windows.MessageBox.Show%2A> Methode der <xref:System.Windows.MessageBox> Klasse. Wenn <xref:System.Windows.MessageBox.Show%2A> wird aufgerufen, die Nachricht ist mit einer Zeichenfolgenparameter übergeben. Verschiedene Überladungen der <xref:System.Windows.MessageBox.Show%2A> ermöglichen Ihnen das Konfigurieren, wie ein Meldungsfeld angezeigt wird (siehe <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Siehe auch  
 [MessageBox-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160023)
