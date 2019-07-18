---
title: 'Vorgehensweise: Öffnen eines Nachrichtenfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: cf7534cdee5e17d53e95294573023d660135e395
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947692"
---
# <a name="how-to-open-a-message-box"></a>Vorgehensweise: Öffnen eines Nachrichtenfelds
Dieses Beispiel zeigt, wie ein Meldungsfeld geöffnet wird.  
  
## <a name="example"></a>Beispiel  
 Ein Meldungsfeld wird eine vorgefertigte modales Dialogfeld für die Anzeige von Informationen für Benutzer. Ein Meldungsfeld wird geöffnet, durch Aufrufen der statischen <xref:System.Windows.MessageBox.Show%2A> Methode der <xref:System.Windows.MessageBox> Klasse. Wenn <xref:System.Windows.MessageBox.Show%2A> wird aufgerufen, wird die Meldung übergeben mit einem String-Parameter. Mehrere Überladungen der <xref:System.Windows.MessageBox.Show%2A> können Sie konfigurieren, wie ein Meldungsfeld angezeigt wird (siehe <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Siehe auch

- [MessageBox-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160023)
