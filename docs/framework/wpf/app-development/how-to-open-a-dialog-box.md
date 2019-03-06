---
title: 'Vorgehensweise: Öffnen eines Dialogfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 1182e22ad40b49ee13832c51986662373f36ee35
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351982"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="fec38-102">Vorgehensweise: Öffnen eines Dialogfelds</span><span class="sxs-lookup"><span data-stu-id="fec38-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="fec38-103">Dieses Beispiel zeigt, wie Sie ein Dialogfeld zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fec38-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fec38-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fec38-104">Example</span></span>  
 <span data-ttu-id="fec38-105">Ein Dialogfeld wird ein Fenster, das durch die Instanziierung geöffnet wird <xref:System.Windows.Window> und das Aufrufen der <xref:System.Windows.Window.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="fec38-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="fec38-106"><xref:System.Windows.Window.ShowDialog%2A> Öffnet ein Fenster, und nicht zurückgegeben, bis das neue Dialogfeld geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="fec38-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="fec38-107">Diese Art von Fenster wird auch bezeichnet als eine *modale* Fenster, und schränkt die Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="fec38-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="fec38-108">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fec38-108">.NET Framework Security</span></span>  
 <span data-ttu-id="fec38-109">Aufrufen von <xref:System.Windows.Window.ShowDialog%2A> erfordert die Berechtigung, die alle Fenster und Benutzereingabeereignisse uneingeschränkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="fec38-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec38-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fec38-110">See also</span></span>
- [<span data-ttu-id="fec38-111">Zurückgeben eines Dialogfeldergebnisses</span><span class="sxs-lookup"><span data-stu-id="fec38-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
