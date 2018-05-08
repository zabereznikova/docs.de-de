---
title: 'Vorgehensweise: Zurückgeben einer Dialogfeldergebnis'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 8f754577a355a58060238bbbb487c36aea14658c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-return-a-dialog-box-result"></a>Vorgehensweise: Zurückgeben einer Dialogfeldergebnis
In diesem Beispiel wird gezeigt, wie das Dialogfeldergebnis für ein Fenster abrufen, die durch Aufrufen von <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Beispiel  
 Bevor Sie ein Dialogfeld wird geschlossen, und seine <xref:System.Windows.Window.DialogResult%2A> Eigenschaft sollte festgelegt werden, mit einer <xref:System.Nullable%601> <xref:System.Boolean> , der angibt, wie der Benutzer das Dialogfeld geschlossen. Dieser Wert wird zurückgegeben, indem <xref:System.Windows.Window.ShowDialog%2A> ermöglicht Clientcode, um zu bestimmen, wie das Dialogfeld geschlossen wurde und folglich wie das Ergebnis zu verarbeiten.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A> kann nur festgelegt werden, wenn ein Fenster, durch den Aufruf geöffnet wurde <xref:System.Windows.Window.ShowDialog%2A>.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Aufrufen von <xref:System.Windows.Window.ShowDialog%2A> erfordert die Berechtigung, alle Fenster und Benutzereingabeereignisse uneingeschränkt verwendet.
