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
ms.openlocfilehash: 1bde7c4f794ca7e3b01490db8e918b06b5074bcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739731"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="94a51-102">Vorgehensweise: Öffnen eines Meldungsfelds</span><span class="sxs-lookup"><span data-stu-id="94a51-102">How to: Open a Message Box</span></span>
<span data-ttu-id="94a51-103">Dieses Beispiel zeigt, wie ein Meldungsfeld geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="94a51-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94a51-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94a51-104">Example</span></span>  
 <span data-ttu-id="94a51-105">Ein Meldungsfeld wird eine vorgefertigte modales Dialogfeld für die Anzeige von Informationen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="94a51-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="94a51-106">Ein Meldungsfeld wird geöffnet, durch Aufrufen der statischen <xref:System.Windows.MessageBox.Show%2A> Methode der <xref:System.Windows.MessageBox> Klasse.</span><span class="sxs-lookup"><span data-stu-id="94a51-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="94a51-107">Wenn <xref:System.Windows.MessageBox.Show%2A> wird aufgerufen, wird die Meldung übergeben mit einem String-Parameter.</span><span class="sxs-lookup"><span data-stu-id="94a51-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="94a51-108">Mehrere Überladungen der <xref:System.Windows.MessageBox.Show%2A> können Sie konfigurieren, wie ein Meldungsfeld angezeigt wird (siehe <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="94a51-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="94a51-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94a51-109">See also</span></span>
- [<span data-ttu-id="94a51-110">MessageBox-Beispiel</span><span class="sxs-lookup"><span data-stu-id="94a51-110">MessageBox Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160023)
