---
title: 'Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters'
description: Verwenden Sie dieses Beispiel, um das Hauptanwendungsfenster in Windows Presentation Foundation (WPF)-Anwendung zu erhalten und festzulegen.
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
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622678"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Gewusst wie: Einrichten und Festlegen des Haupt Anwendungsfensters
In diesem Beispiel wird gezeigt, wie das Hauptanwendungsfenster von Get und festgelegt wird.  
  
## <a name="example"></a>Beispiel  
 Der erste <xref:System.Windows.Window> , der in einer Windows Presentation Foundation (WPF)-Anwendung instanziiert wird, wird von automatisch <xref:System.Windows.Application> als Hauptanwendungsfenster festgelegt. Der erste <xref:System.Windows.Window> zu instanziierte ist wahrscheinlich das Fenster, das als URI (Uniform Resource Identifier) für den Startup angegeben wird (siehe <xref:System.Windows.Application.StartupUri%2A> ).  
  
 Der erste <xref:System.Windows.Window> kann auch mit Code instanziiert werden. Ein Beispiel ist das Öffnen eines Fensters während des Anwendungs Starts, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 Manchmal ist die erste instanziierte <xref:System.Windows.Window> nicht tatsächlich das Hauptanwendungsfenster, z. b. ein Begrüßungsbildschirm. In diesem Fall können Sie das Hauptanwendungsfenster mithilfe von Markup angeben, wie im folgenden Beispiel:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Unabhängig davon, ob das Hauptfenster automatisch oder manuell angegeben wird, können Sie das Hauptfenster <xref:System.Windows.Application.MainWindow%2A> wie folgt aus dem folgenden Code verwenden:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
