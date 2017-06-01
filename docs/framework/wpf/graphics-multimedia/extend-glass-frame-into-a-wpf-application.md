---
title: "Erweitern von Glasframe in eine WPF-Anwendung | Microsoft Docs"
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
  - "Anwendungen, Erweitern von Glasframes in"
  - "Erweitern von Glasframes in Anwendungen"
  - "Glasframes, Erweitern in Anwendungen"
  - "Grafiken, Erweitern von Glasframes in Anwendungen"
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Erweitern von Glasframe in eine WPF-Anwendung
In diesem Thema wird veranschaulicht, wie Sie einen [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]\-Glasframe in den Clientbereich einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendung erweitern.  
  
> [!NOTE]
>  Dieses Beispiel funktioniert nur auf einem [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]\-Computer, auf dem der Desktopfenster\-Manager \(DWM\) mit aktiviertem Glaseffekt ausgeführt wird.  [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Home Basic\-Edition unterstützt den transparenten Glaseffekt nicht.  Bereiche, die in anderen Editionen von [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] normalerweise mit dem transparenten Glaseffekt gerendert werden würden, werden nicht transparent gerendert.  
  
## Beispiel  
 Die folgende Abbildung zeigt den in die Adressleiste von Internet Explorer 7 erweiterten Glasframe.  
  
 ****Internet Explorer mit erweitertem Glasframe hinter der Adressleiste.****  
  
 ![IE7 mit sich hinter die Adressleiste ausdehnendem Glasrahmen](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")  
  
 Um den Glasframe in eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung zu erweitern, ist der Zugriff auf die unverwaltete [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] erforderlich.  Das folgende Codebeispiel führt einen Plattformaufruf \(pinvoke\) für die beiden [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]s aus, die erforderlich sind, um den Frame in den Clientbereich zu erweitern.  Jede dieser [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]s wird in einer Klasse mit dem Namen **NonClientRegionAPI** deklariert.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#DWMExtendFramePInvokeAPI](AvalonClientGlass#DWMExtendFramePInvokeAPI)]  -->  
  
 [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea) [](_udwm_dwmextendframeintoclientarea) ist die DWM\-Funktion, die den Frame in den Clientbereich erweitert.  Es werden zwei Parameter übernommen: ein Fensterhandle und eine [MARGINS](inet_MARGINS)\-Struktur.  [MARGINS](inet_MARGINS) legt für den DWM fest, wie weit der Frame in den Clientbereich erweitert werden soll.  
  
## Beispiel  
 Um die [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea)\-Funktion zu verwenden, muss ein Fensterhandle abgerufen werden.  In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kann das Fensterhandle aus der <xref:System.Windows.Interop.HwndSource.Handle%2A>\-Eigenschaft einer <xref:System.Windows.Interop.HwndSource> abgerufen werden.  Im folgenden Beispiel wird der Frame in den Clientbereich des <xref:System.Windows.FrameworkElement.Loaded>\-Ereignisses des Fensters erweitert.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#AvalonGlassOnLoadedCSharp](AvalonClientGlass#AvalonGlassOnLoadedCSharp)]  -->  
  
## Beispiel  
 Das folgende Beispiel zeigt ein einfaches Fenster, in dem der Frame in den Clientbereich erweitert wird.  Der Frame wird hinter dem oberen Rand erweitert, der die beiden <xref:System.Windows.Controls.TextBox>\-Objekte enthält.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#AvalonGlassFullWindowXAML](AvalonClientGlass#AvalonGlassFullWindowXAML)]  -->  
  
 Die folgende Abbildung zeigt den in eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung erweiterten Glasframe.  
  
 **In eine**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] **\-Anwendung erweiterter Glasframe.**  
  
 ![In eine WPF&#45;Anwendung erweiterter Glasframe](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.png "WPFextendedGlassIntoClient")  
  
## Siehe auch  
 [Übersicht über den Desktopfenster\-Manager](_udwm_overview)   
 [Übersicht über den Desktopfenster\-Manager\-Weichzeichner](_udwm_blur_ovw)   
 [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea)