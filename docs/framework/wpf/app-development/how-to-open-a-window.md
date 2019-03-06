---
title: 'Vorgehensweise: Öffnen Sie ein Fenster'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373568"
---
# <a name="how-to-open-a-window"></a>Vorgehensweise: Öffnen Sie ein Fenster
Dieses Beispiel zeigt, wie Sie ein Fenster zu öffnen.  
  
## <a name="example"></a>Beispiel  
 Ein Fenster wird geöffnet, durch die Instanziierung <xref:System.Windows.Window> und das Aufrufen der <xref:System.Windows.Window.Show%2A> Methode. <xref:System.Windows.Window.Show%2A> Öffnet ein Fenster und kehrt sofort zurück, ohne zu warten, für das neue Fenster zu schließen. Diese Art von Fenster wird auch bezeichnet als eine *nicht modale* Fenster, und schränkt keine Benutzereingaben.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Instanziieren von <xref:System.Windows.Window> erfordert die Berechtigung auf unsafe native Methoden aufzurufen (finden Sie unter <xref:System.Windows.Window.%23ctor%2A>).
