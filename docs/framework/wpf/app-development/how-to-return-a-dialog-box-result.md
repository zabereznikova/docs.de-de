---
title: 'Vorgehensweise: Zurückgeben eines Dialogfeldergebnisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: b574a5bbc08d947371837116915c2fc8c13ec81d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357767"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="f68a7-102">Vorgehensweise: Zurückgeben eines Dialogfeldergebnisses</span><span class="sxs-lookup"><span data-stu-id="f68a7-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="f68a7-103">Dieses Beispiel zeigt, wie Sie das Dialogergebnis für ein Fenster abrufen, die durch den Aufruf geöffnet wird <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="f68a7-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f68a7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f68a7-104">Example</span></span>  
 <span data-ttu-id="f68a7-105">Bevor Sie ein Dialogfeld wird geschlossen, und seine <xref:System.Windows.Window.DialogResult%2A> legen Sie mit einer <xref:System.Nullable%601> <xref:System.Boolean> , der angibt, wie der Benutzer das Dialogfeld geschlossen.</span><span class="sxs-lookup"><span data-stu-id="f68a7-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="f68a7-106">Dieser Wert wird zurückgegeben, indem <xref:System.Windows.Window.ShowDialog%2A> damit Clientcode, um zu bestimmen, wie Sie das Dialogfeld geschlossen wurde und folglich wie das Ergebnis verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f68a7-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f68a7-107"><xref:System.Windows.Window.DialogResult%2A> kann nur festgelegt werden, wenn ein Fenster, durch den Aufruf geöffnet wurde <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="f68a7-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="f68a7-108">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f68a7-108">.NET Framework Security</span></span>  
 <span data-ttu-id="f68a7-109">Aufrufen von <xref:System.Windows.Window.ShowDialog%2A> erfordert die Berechtigung, die alle Fenster und Benutzereingabeereignisse uneingeschränkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="f68a7-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
