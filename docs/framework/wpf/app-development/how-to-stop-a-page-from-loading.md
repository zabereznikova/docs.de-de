---
title: 'Vorgehensweise: Beenden des Ladens eine Seite'
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
- pages [WPF], stopping from loading
- methods [WPF], Stoploading
- events [WPF], NavigationStopped
- NavigationStopped properties [WPF]
- stopping pages from loading [WPF]
- loading [WPF], stopping
ms.assetid: e2b695b0-517e-462c-8ccf-90cc8d6ba864
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b68936ed83a61fc6d4c80408bd055c0eb05e030d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-stop-a-page-from-loading"></a>Vorgehensweise: Beenden des Ladens eine Seite
In diesem Beispiel wird gezeigt, wie zum Aufrufen der <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> Methode, um die Navigation zu Inhalt zu beenden, bevor er abgeschlossen wurde, wird heruntergeladen.  
  
## <a name="example"></a>Beispiel  
 <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A>Stoppt das Herunterladen des angeforderten Inhalts und bewirkt, dass die <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> Ereignis ausgelöst wurde.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatestoploadingcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatestoploadingcode)]
