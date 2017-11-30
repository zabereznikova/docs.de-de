---
title: 'Vorgehensweise: Abrufen und Festlegen des Hauptfensters der Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d6bca158172fd3fc31526287c6d4a9928a8ea0c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Vorgehensweise: Abrufen und Festlegen des Hauptfensters der Anwendung
Dieses Beispiel zeigt, wie zum Abrufen und Festlegen des Hauptfensters der Anwendung.  
  
## <a name="example"></a>Beispiel  
 Die erste <xref:System.Windows.Window> instanziiert, die innerhalb einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Anwendung automatisch festlegen, indem <xref:System.Windows.Application> als Hauptfenster der Anwendung. Die erste <xref:System.Windows.Window> instanziiert wird sehr wahrscheinlich werden, werden die Fenster, das als Start-angegeben wird [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (finden Sie unter <xref:System.Windows.Application.StartupUri%2A>).  
  
 Die erste <xref:System.Windows.Window> könnte auch mithilfe von Code instanziiert werden. Ein Beispiel ist ein Fenster während des Anwendungsstarts wie folgt öffnen:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 In manchen Fällen das erste instanziiert <xref:System.Windows.Window> wird nicht tatsächlich das Hauptanwendungsfenster z. B. einen Begrüßungsbildschirm. In diesem Fall können Sie das Hauptanwendungsfenster mit Markup wie folgt angeben:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Ob das Hauptfenster automatisch oder manuell angegeben wird, erhalten Sie im Hauptfenster von <xref:System.Windows.Application.MainWindow%2A> mit dem folgenden Code, wie folgt:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
