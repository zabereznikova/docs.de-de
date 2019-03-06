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
# <a name="how-to-return-a-dialog-box-result"></a>Vorgehensweise: Zurückgeben eines Dialogfeldergebnisses
Dieses Beispiel zeigt, wie Sie das Dialogergebnis für ein Fenster abrufen, die durch den Aufruf geöffnet wird <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Beispiel  
 Bevor Sie ein Dialogfeld wird geschlossen, und seine <xref:System.Windows.Window.DialogResult%2A> legen Sie mit einer <xref:System.Nullable%601> <xref:System.Boolean> , der angibt, wie der Benutzer das Dialogfeld geschlossen. Dieser Wert wird zurückgegeben, indem <xref:System.Windows.Window.ShowDialog%2A> damit Clientcode, um zu bestimmen, wie Sie das Dialogfeld geschlossen wurde und folglich wie das Ergebnis verarbeitet.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A> kann nur festgelegt werden, wenn ein Fenster, durch den Aufruf geöffnet wurde <xref:System.Windows.Window.ShowDialog%2A>.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Aufrufen von <xref:System.Windows.Window.ShowDialog%2A> erfordert die Berechtigung, die alle Fenster und Benutzereingabeereignisse uneingeschränkt verwenden.
