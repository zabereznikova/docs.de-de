---
title: "Gewusst wie: Verwenden von SystemFonts | Microsoft Docs"
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
  - "Schriftarten, Systemschriftarten"
  - "Systemschriftarten"
  - "SystemFonts-Klasse"
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Gewusst wie: Verwenden von SystemFonts
In diesem Beispiel wird die Verwendung der statischen Ressourcen der <xref:System.Windows.SystemFonts>\-Klasse zum Formatieren oder Anpassen einer Schaltfläche veranschaulicht.  
  
## Beispiel  
 Systemressourcen machen mehrere vom System festgelegte Werte als Ressourcen und Eigenschaften verfügbar, damit Sie visuelle Objekte erstellen können, die den Systemeinstellungen entsprechen.  <xref:System.Windows.SystemFonts> ist eine Klasse, die sowohl Systemschriftartwerte als statische Eigenschaften als auch Eigenschaften enthält, die auf Ressourcenschlüssel verweisen. Diese Ressourcenschlüssel können zur Laufzeit für den dynamischen Zugriff auf diese Werte verwendet werden.  Beispielsweise ist <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ein <xref:System.Windows.SystemFonts>\-Wert und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> ein entsprechender Ressourcenschlüssel.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie die Member von <xref:System.Windows.SystemFonts> entweder als statische Eigenschaften oder als dynamische Ressourcenverweise verwenden \(wobei der statische Eigenschaftswert als Schlüssel dient\).  Verwenden Sie einen dynamischen Ressourcenverweis, wenn die Schriftartmetrik beim Ausführen der Anwendung automatisch aktualisiert werden soll. Verwenden Sie andernfalls einen statischen Wertverweis.  
  
> [!NOTE]
>  Bei Ressourcenschlüsseln wird das Suffix "Key" an den Eigenschaftennamen gehängt.  
  
 Das folgende Beispiel veranschaulicht den Zugriff auf und die Verwendung der Eigenschaften von <xref:System.Windows.SystemFonts> als statische Werte zum Formatieren oder Anpassen einer Schaltfläche.  In diesem Markupbeispiel werden einer Schaltfläche <xref:System.Windows.SystemFonts>\-Werte zugewiesen.  
  
 [!code-xml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Um die Werte von <xref:System.Windows.SystemFonts> im Code verwenden zu können, ist es nicht erforderlich, einen statischen Wert oder dynamischen Ressourcenverweis zu verwenden.  Verwenden Sie stattdessen die Nicht\-Schlüsseleigenschaften der <xref:System.Windows.SystemFonts>\-Klasse.  Obwohl die Nicht\-Schlüsseleigenschaften anscheinend als statische Eigenschaften definiert sind, gilt für das Laufzeitverhalten des vom System gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], dass die Eigenschaften in Echtzeit neu ausgewertet und vom Benutzer ausgelöste Änderungen an Systemwerten entsprechend berücksichtigt werden.  Das folgende Beispiel veranschaulicht, wie die Schriftarteinstellungen einer Schaltfläche angegeben werden.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## Siehe auch  
 <xref:System.Windows.SystemFonts>   
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Verwenden von SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)   
 [Verwenden von Systemschriftartschlüsseln](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)   
 [x:Statische Markuperweiterung](../../../../docs/framework/xaml-services/x-static-markup-extension.md)   
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [DynamicResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)