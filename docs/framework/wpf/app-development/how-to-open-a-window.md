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
ms.openlocfilehash: 23dc74666d8f47a0fb735d96ad22ed56c96bdbc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545463"
---
# <a name="how-to-open-a-window"></a>Vorgehensweise: Öffnen Sie ein Fenster
In diesem Beispiel wird gezeigt, wie ein Fenster geöffnet wird.  
  
## <a name="example"></a>Beispiel  
 Ein Fenster wird geöffnet, durch die Instanziierung <xref:System.Windows.Window> und Aufrufen der <xref:System.Windows.Window.Show%2A> Methode. <xref:System.Windows.Window.Show%2A> Öffnet ein Fenster und kehrt sofort zurück, ohne zu warten, für das neue Fenster zu schließen. Diese Art von Fenster ist auch bekannt als ein *nicht modalen* Fenster, und schränkt keine Benutzereingaben.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Instanziieren <xref:System.Windows.Window> erfordert die Berechtigung zum Aufruf von unsicheren systemeigener Methoden (siehe <xref:System.Windows.Window.%23ctor%2A>).
