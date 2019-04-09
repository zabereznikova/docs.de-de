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
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084973"
---
# <a name="how-to-open-a-dialog-box"></a>Vorgehensweise: Öffnen eines Dialogfelds
Dieses Beispiel zeigt, wie Sie ein Dialogfeld zu öffnen.  
  
## <a name="example"></a>Beispiel  
 Ein Dialogfeld wird ein Fenster, das durch die Instanziierung geöffnet wird <xref:System.Windows.Window> und das Aufrufen der <xref:System.Windows.Window.ShowDialog%2A> Methode. <xref:System.Windows.Window.ShowDialog%2A> Öffnet ein Fenster, und nicht zurückgegeben, bis das neue Dialogfeld geschlossen wurde. Diese Art von Fenster wird auch bezeichnet als eine *modale* Fenster, und schränkt die Benutzereingabe.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Aufrufen von <xref:System.Windows.Window.ShowDialog%2A> erfordert die Berechtigung, die alle Fenster und Benutzereingabeereignisse uneingeschränkt verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Zurückgeben eines Dialogfeldergebnisses](how-to-return-a-dialog-box-result.md)
