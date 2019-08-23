---
title: 'Vorgehensweise: Zurückgeben eines Dialogfeldergebnisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968233"
---
# <a name="how-to-return-a-dialog-box-result"></a>Vorgehensweise: Zurückgeben eines Dialogfeldergebnisses
Dieses Beispiel zeigt, wie das Dialogfeld Ergebnis für ein Fenster abgerufen wird, das durch <xref:System.Windows.Window.ShowDialog%2A>Aufrufen von geöffnet wird.  
  
## <a name="example"></a>Beispiel  
 Bevor ein Dialogfeld geschlossen wird, <xref:System.Windows.Window.DialogResult%2A> sollte seine-Eigenschaft mit einem <xref:System.Nullable%601> <xref:System.Boolean> festgelegt werden, das angibt, wie der Benutzer das Dialogfeld geschlossen hat. Dieser Wert wird von <xref:System.Windows.Window.ShowDialog%2A> zurückgegeben, damit Client Code bestimmen kann, wie das Dialogfeld geschlossen wurde, und damit das Ergebnis verarbeitet wird.  
  
> [!NOTE]
> <xref:System.Windows.Window.DialogResult%2A>kann nur festgelegt werden, wenn ein Fenster durch Aufrufen <xref:System.Windows.Window.ShowDialog%2A>von geöffnet wurde.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Der <xref:System.Windows.Window.ShowDialog%2A> Aufruf von erfordert die Berechtigung, alle Windows-und Benutzereingabe Ereignisse ohne Einschränkung zu verwenden.
