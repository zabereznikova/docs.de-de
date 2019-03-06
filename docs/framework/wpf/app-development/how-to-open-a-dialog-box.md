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
