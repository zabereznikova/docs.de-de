---
title: 'Vorgehensweise: Öffnen eines Meldungsfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: f05190030ed6324917348fa1926abd5385e30f7e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274686"
---
# <a name="how-to-open-a-message-box"></a>Vorgehensweise: Öffnen eines Meldungsfelds
Dieses Beispiel zeigt, wie ein Meldungsfeld geöffnet wird.  
  
## <a name="example"></a>Beispiel  
 Ein Meldungsfeld wird eine vorgefertigte modales Dialogfeld für die Anzeige von Informationen für Benutzer. Ein Meldungsfeld wird geöffnet, durch Aufrufen der statischen <xref:System.Windows.MessageBox.Show%2A> Methode der <xref:System.Windows.MessageBox> Klasse. Wenn <xref:System.Windows.MessageBox.Show%2A> wird aufgerufen, wird die Meldung übergeben mit einem String-Parameter. Mehrere Überladungen der <xref:System.Windows.MessageBox.Show%2A> können Sie konfigurieren, wie ein Meldungsfeld angezeigt wird (siehe <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Siehe auch  
 [MessageBox-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160023)
