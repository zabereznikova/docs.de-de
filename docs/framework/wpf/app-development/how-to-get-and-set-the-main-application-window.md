---
title: 'Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582548"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters
In diesem Beispiel wird gezeigt, wie das Hauptanwendungsfenster von Get und festgelegt wird.  
  
## <a name="example"></a>Beispiel  
 Der erste <xref:System.Windows.Window>, der in einer Windows Presentation Foundation (WPF)-Anwendung instanziiert wird, wird automatisch von <xref:System.Windows.Application> als Hauptanwendungsfenster festgelegt. Der erste <xref:System.Windows.Window>, der instanziiert werden soll, ist wahrscheinlich das Fenster, das als URI (Uniform Resource Identifier) für den Startup angegeben wird (siehe <xref:System.Windows.Application.StartupUri%2A>).  
  
 Der erste <xref:System.Windows.Window> kann auch mit Code instanziiert werden. Ein Beispiel ist das Öffnen eines Fensters während des Anwendungs Starts, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 Manchmal ist die erste instanziierte <xref:System.Windows.Window> nicht das Hauptanwendungsfenster, z. b. ein Begrüßungsbildschirm. In diesem Fall können Sie das Hauptanwendungsfenster mithilfe von Markup angeben, wie im folgenden Beispiel:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Unabhängig davon, ob das Hauptfenster automatisch oder manuell angegeben wird, können Sie das Hauptfenster aus <xref:System.Windows.Application.MainWindow%2A> mit dem folgenden Code erhalten, wie im folgenden Beispiel:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
