---
title: 'Vorgehensweise: Öffnen eines Meldungs Felds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123726"
---
# <a name="how-to-open-a-message-box"></a>Vorgehensweise: Öffnen eines Meldungs Felds
Dieses Beispiel zeigt, wie ein Meldungs Feld geöffnet wird.  
  
## <a name="example"></a>Beispiel  
 Ein Meldungs Feld ist ein vorgefertigtes modales Dialogfeld zum Anzeigen von Informationen für Benutzer. Ein Meldungs Feld wird geöffnet, indem die statische <xref:System.Windows.MessageBox.Show%2A>-Methode der <xref:System.Windows.MessageBox>-Klasse aufgerufen wird. Wenn <xref:System.Windows.MessageBox.Show%2A> aufgerufen wird, wird die Nachricht mit einem Zeichen folgen Parameter übergeben. Mit mehreren über Ladungen von <xref:System.Windows.MessageBox.Show%2A> können Sie konfigurieren, wie ein Meldungs Feld angezeigt wird (siehe <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Weitere Informationen

- [MessageBox-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
