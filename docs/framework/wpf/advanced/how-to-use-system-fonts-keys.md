---
title: "Gewusst wie: Verwenden von Systemschriftartschl&#252;sseln | Microsoft Docs"
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
  - "Klassen, SystemFonts"
  - "Ressourcenschlüssel, SystemFonts-Klasse"
  - "SystemFonts-Klasse"
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Verwenden von Systemschriftartschl&#252;sseln
Systemressourcen machen verschiedene Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Objekte erstellen können, die den Systemeinstellungen entsprechen.  <xref:System.Windows.SystemFonts> ist eine Klasse, die sowohl Systemschriftartwerte als auch Systemschriftartressourcen enthält, die an die Werte gebunden werden, zum Beispiel <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Systemschriftartmetriken können als statische oder dynamische Ressourcen verwendet werden.  Verwenden Sie eine dynamische Ressource, wenn die Schriftartmetrik beim Ausführen der Anwendung automatisch aktualisiert werden soll. Verwenden Sie andernfalls eine statische Ressource.  
  
> [!NOTE]
>  Bei dynamischen Ressourcen ist das Schlüsselwort *Key* an den Eigenschaftennamen angefügt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie auf dynamische Ressourcen der Systemschriftart zugegriffen werden kann und wie sie sich verwenden lassen, um eine Schaltfläche zu formatieren oder anzupassen.  In diesem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Beispiel wird ein Schaltflächenformat erstellt, das einer Schaltfläche <xref:System.Windows.SystemFonts>\-Werte zuordnet.  
  
## Beispiel  
 [!code-xml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## Siehe auch  
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Verwenden von SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)   
 [Verwenden von SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)