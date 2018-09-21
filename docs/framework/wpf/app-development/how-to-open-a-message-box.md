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
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46507777"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="eb32b-102">Vorgehensweise: Öffnen eines Meldungsfelds</span><span class="sxs-lookup"><span data-stu-id="eb32b-102">How to: Open a Message Box</span></span>
<span data-ttu-id="eb32b-103">Dieses Beispiel zeigt, wie ein Meldungsfeld geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="eb32b-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb32b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb32b-104">Example</span></span>  
 <span data-ttu-id="eb32b-105">Ein Meldungsfeld wird eine vorgefertigte modales Dialogfeld für die Anzeige von Informationen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eb32b-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="eb32b-106">Ein Meldungsfeld wird geöffnet, durch Aufrufen der statischen <xref:System.Windows.MessageBox.Show%2A> Methode der <xref:System.Windows.MessageBox> Klasse.</span><span class="sxs-lookup"><span data-stu-id="eb32b-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="eb32b-107">Wenn <xref:System.Windows.MessageBox.Show%2A> wird aufgerufen, wird die Meldung übergeben mit einem String-Parameter.</span><span class="sxs-lookup"><span data-stu-id="eb32b-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="eb32b-108">Mehrere Überladungen der <xref:System.Windows.MessageBox.Show%2A> können Sie konfigurieren, wie ein Meldungsfeld angezeigt wird (siehe <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="eb32b-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="eb32b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb32b-109">See Also</span></span>  
 [<span data-ttu-id="eb32b-110">MessageBox-Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb32b-110">MessageBox Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160023)
