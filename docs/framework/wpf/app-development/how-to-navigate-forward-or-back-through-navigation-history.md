---
title: "Gewusst wie: Vorw&#228;rts- oder R&#252;ckw&#228;rtsnavigation mit dem Navigationsverlauf | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verlauf, Navigation, Vorwärtsnavigation"
  - "Navigation, Mit Navigationsverlauf (vorwärts)"
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Vorw&#228;rts- oder R&#252;ckw&#228;rtsnavigation mit dem Navigationsverlauf
Dieses Beispiel zeigt, wie Sie zurück zu Einträgen vorwärts oder im Navigationsverlauf navigiert.  
  
## Beispiel  
 Code, der vom Inhalt in den folgenden Hosts ausgeführt wird, kann vorwärts oder Back durchgehenden Navigationsverlauf, einen Eintrag für Eintrag navigieren.  
  
-   <xref:System.Windows.Navigation.NavigationWindow> mit <xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame> mit <xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Bevor Sie Eintrag Vorwärts navigieren können, müssen Sie zunächst überprüfen, ob Einträge im Navigationsverlauf vor gibt, indem Sie die **CanGoForward**\-Eigenschaft überprüfen.  Zum Einstieg vorwärts zu navigieren, rufen Sie die **GoForward**\-Methode auf.  Dies ist im folgenden Codebeispiel gezeigt:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Bevor Sie eine der Eintrag navigieren können, müssen Sie zunächst überprüfen, ob Einträge im Navigationsverlauf zurück gibt, indem Sie die **CanGoBack**\-Eigenschaft überprüfen.  Um Eintrag der eine zu navigieren, rufen Sie die **GoBack**\-Methode auf.  Dies ist im folgenden Codebeispiel gezeigt:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**und **GoBack** werden durch <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationService>implementiert.  
  
> [!NOTE]
>  Wenn Sie **GoForward**aufrufen und keine Einträge im Navigationsverlauf vor gibt, oder wenn Sie **GoBack**aufrufen und keine Einträge im Navigationsverlauf zurück <xref:System.InvalidOperationException> sind, wird ausgelöst.