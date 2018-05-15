---
title: 'Vorgehensweise: Öffnen des Dialogfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 29fe8b0d516f20fcc742b91099a30e368dfe4548
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="8743e-102">Vorgehensweise: Öffnen des Dialogfelds</span><span class="sxs-lookup"><span data-stu-id="8743e-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="8743e-103">In diesem Beispiel wird gezeigt, wie ein Dialogfeld geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="8743e-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8743e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8743e-104">Example</span></span>  
 <span data-ttu-id="8743e-105">Ein Dialogfeld wird ein Fenster, das durch Instanziierung geöffnet wird <xref:System.Windows.Window> und Aufrufen der <xref:System.Windows.Window.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="8743e-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="8743e-106"><xref:System.Windows.Window.ShowDialog%2A> Öffnet ein Fenster, und gibt zurück, bis das neue Dialogfeld geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8743e-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="8743e-107">Diese Art von Fenster ist auch bekannt als ein *modale* Fenster, und schränkt Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="8743e-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="8743e-108">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8743e-108">.NET Framework Security</span></span>  
 <span data-ttu-id="8743e-109">Aufrufen von <xref:System.Windows.Window.ShowDialog%2A> erfordert die Berechtigung, alle Fenster und Benutzereingabeereignisse uneingeschränkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="8743e-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8743e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8743e-110">See Also</span></span>  
 [<span data-ttu-id="8743e-111">Zurückgeben eines Dialogfeldergebnisses</span><span class="sxs-lookup"><span data-stu-id="8743e-111">Return a Dialog Box Result</span></span>](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
