---
title: "Optimieren der Leistung: Weitere Empfehlungen | Microsoft Docs"
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
  - "Pinsel, Leistung"
  - "Treffertests für Objekte [WPF]"
  - "Durchlässigkeit"
  - "ScrollBarVisibility-Enumeration"
  - "Rendering für Terminaldienste"
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Optimieren der Leistung: Weitere Empfehlungen
<a name="introduction"></a> Dieses Thema enthält zusätzlich zu den in den Themen des Abschnitts [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md) beschriebenen Empfehlungen weitere Empfehlungen zur Leistungsoptimierung.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Durchlässigkeit für Pinsel oder Durchlässigkeit für Elemente](#Opacity)  
  
-   [Navigation zu Objekt](#Navigation_Objects)  
  
-   [Treffertests für große 3D\-Oberflächen](#Hit_Testing)  
  
-   [CompositionTarget.Rendering\-Ereignis](#CompositionTarget_Rendering_Event)  
  
-   [Vermeiden der Verwendung von ScrollBarVisibility\=Auto](#Avoid_Using_ScrollBarVisibility)  
  
-   [Konfigurieren des Schriftartcachediensts zum Reduzieren der Startzeit](#FontCache)  
  
<a name="Opacity"></a>   
## Durchlässigkeit für Pinsel oder Durchlässigkeit für Elemente  
 Wenn Sie mit einem <xref:System.Windows.Media.Brush> den <xref:System.Windows.Shapes.Shape.Fill%2A>\-Wert oder den <xref:System.Windows.Shapes.Shape.Stroke%2A>\-Wert eines Elements festlegen, empfiehlt es sich, den <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=fullName>\-Wert statt der Einstellung der <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft des Elements festzulegen.  Wenn die <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft eines Elements geändert wird, erstellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] möglicherweise eine temporäre Oberfläche.  
  
<a name="Navigation_Objects"></a>   
## Navigation zu Objekt  
 Das <xref:System.Windows.Navigation.NavigationWindow>\-Objekt wird von <xref:System.Windows.Window> abgeleitet und erweitert es mit Inhaltsnavigationsunterstützung. Dabei werden in erster Linie <xref:System.Windows.Navigation.NavigationService> und das Journal aggregiert.  Sie können den Clientbereich von <xref:System.Windows.Navigation.NavigationWindow> aktualisieren, indem Sie entweder einen [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] oder ein Objekt angeben.  Im folgenden Beispiel werden beide Methoden veranschaulicht:  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Jedes <xref:System.Windows.Navigation.NavigationWindow>\-Objekt verfügt über ein Journal, das den Navigationsverlauf des Benutzers in diesem Fenster aufzeichnet.  Ein Zweck des Journals besteht darin, Benutzern das Zurückverfolgen ihrer Schritte zu ermöglichen.  
  
 Wenn Sie mit einem [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] navigieren, speichert das Journal nur den [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]\-Verweis.  Dies bedeutet, dass die Seite bei jedem erneuten Besuch dynamisch rekonstruiert wird, was je nach Komplexität der Seite sehr zeitaufwändig sein kann.  In diesem Fall sind die Kosten für die Journalspeicherung zwar gering, der Zeitaufwand für die Wiederherstellung der Seite ist jedoch potenziell sehr hoch.  
  
 Wenn Sie mit einem Objekt navigieren, speichert das Journal die ganze visuelle Struktur des Objekts.  Dies bedeutet, dass die Seite bei jedem erneuten Besuch sofort gerendert wird, ohne dass sie rekonstruiert werden muss.  In diesem Fall sind die Kosten für die Journalspeicherung hoch, der Zeitaufwand für die Wiederherstellung der Seite ist jedoch gering.  
  
 Beim Verwenden des <xref:System.Windows.Navigation.NavigationWindow>\-Objekts müssen Sie bedenken, wie durch die Journalunterstützung die Leistung der Anwendung beeinflusst wird.  Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## Treffertests für große 3D\-Oberflächen  
 Die Treffertests für große 3D\-Oberflächen stellen hinsichtlich der CPU\-Auslastung einen sehr ressourcenintensiven Vorgang dar.  Dies gilt insbesondere, wenn die 3D\-Oberfläche animiert ist.  Deaktivieren Sie die Treffertests, wenn Sie keine Treffertests für diese Oberflächen benötigen.  Objekte, die von <xref:System.Windows.UIElement> abgeleitet werden, können die Treffertests deaktivieren, indem sie die <xref:System.Windows.UIElement.IsHitTestVisible%2A>\-Eigenschaft auf `false` festlegen.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## CompositionTarget.Rendering\-Ereignis  
 Das <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=fullName>\-Ereignis bewirkt, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fortlaufend animiert.  Wenn Sie dieses Ereignis verwenden, trennen Sie es bei jeder Gelegenheit.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## Vermeiden der Verwendung von ScrollBarVisibility\=Auto  
 Vermeiden Sie nach Möglichkeit die Verwendung des <xref:System.Windows.Controls.ScrollBarVisibility?displayProperty=fullName>\-Werts für die Eigenschaften `HorizontalScrollBarVisibility` und `VerticalScrollBarVisibility`.  Diese Eigenschaften werden für <xref:System.Windows.Controls.RichTextBox>\-Objekte, <xref:System.Windows.Controls.ScrollViewer>\-Objekte und <xref:System.Windows.Controls.TextBox>\-Objekte sowie als angefügte Eigenschaft für das <xref:System.Windows.Controls.ListBox>\-Objekt definiert.  Legen Sie stattdessen <xref:System.Windows.Controls.ScrollBarVisibility> auf <xref:System.Windows.Controls.ScrollBarVisibility>, <xref:System.Windows.Controls.ScrollBarVisibility> oder <xref:System.Windows.Controls.ScrollBarVisibility> fest.  
  
 Der <xref:System.Windows.Controls.ScrollBarVisibility>\-Wert ist für Fälle vorgesehen, in denen der Platz beschränkt ist und Symbolleisten nur bei Bedarf angezeigt werden sollen.  Zum Beispiel kann es sinnvoll sein, diesen <xref:System.Windows.Controls.ScrollBarVisibility>\-Wert für ein <xref:System.Windows.Controls.ListBox> mit 30 Elementen anstatt für ein <xref:System.Windows.Controls.TextBox> mit Hunderten von Textzeilen zu verwenden.  
  
<a name="FontCache"></a>   
## Konfigurieren des Schriftartcachediensts zum Reduzieren der Startzeit  
 Der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Schriftartcachedienst nutzt Schriftartdaten zwischen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen.  Die erste [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung, die Sie ausführen, startet diesen Dienst, wenn er nicht bereits ausgeführt wird.  Bei [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] können Sie den Dienst "[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Schriftartcache 3.0.0.0" von "Manuell" \(Standard\) auf "Automatisch \(Verzögerter Start\)" festlegen, um die anfängliche Startzeit von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen zu reduzieren.  
  
## Siehe auch  
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Nutzen der Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Projektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Tipps und Tricks zu Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)