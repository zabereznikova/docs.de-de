---
title: "Gewusst wie: Verwenden von SystemParameters | Microsoft Docs"
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
  - "Klassen, SystemParameters"
  - "SystemParameters-Klasse"
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Gewusst wie: Verwenden von SystemParameters
Dieses Beispiel veranschaulicht den Zugriff auf und die Verwendung der Eigenschaften von <xref:System.Windows.SystemParameters> zum Formatieren oder Anpassen einer Schaltfläche.  
  
## Beispiel  
 Systemressourcen machen verschiedene systembasierte Einstellungen als Ressourcen verfügbar, damit Sie visuelle Objekte erstellen können, die den Systemeinstellungen entsprechen.  <xref:System.Windows.SystemParameters> ist eine Klasse, die sowohl Eigenschaftswerte von Systemparametern als auch Ressourcenschlüssel enthält, die an die Werte gebunden werden.  Zum Beispiel ist <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> ein <xref:System.Windows.SystemParameters>\-Eigenschaftswert und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> der entsprechende Ressourcenschlüssel.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Sie die Member von <xref:System.Windows.SystemParameters> entweder als statische Eigenschaft oder als dynamischen Ressourcenverweis verwenden \(wobei der statische Eigenschaftswert als Schlüssel dient\).  Verwenden Sie einen dynamischen Ressourcenverweis, wenn der systembasierte Wert automatisch aktualisiert werden soll, während die Anwendung ausgeführt wird. Andernfalls verwenden Sie einen statischen Verweis.  Bei Ressourcenschlüsseln wird das Suffix `Key` an den Eigenschaftennamen gehängt.  
  
 Das folgende Beispiel veranschaulicht den Zugriff auf und die Verwendung der statischen Werte von <xref:System.Windows.SystemParameters> zum Formatieren oder Anpassen einer Schaltfläche.  In diesem Markupbeispiel wird die Größe einer Schaltfläche angepasst, indem <xref:System.Windows.SystemParameters>\-Werte auf eine Schaltfläche angewendet werden.  
  
 [!code-xml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Um die Werte von <xref:System.Windows.SystemParameters> im Code verwenden zu können, ist es nicht erforderlich, statische Verweise oder dynamische Ressourcenverweise zu verwenden.  Verwenden Sie stattdessen die Werte der <xref:System.Windows.SystemParameters>\-Klasse.  Obwohl die Nicht\-Schlüsseleigenschaften anscheinend als statische Eigenschaften definiert sind, wertet das vom System gehostete [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Laufzeitverhalten die Eigenschaften in Echtzeit erneut aus, und vom Benutzer ausgelöste Änderungen von Systemwerten werden berücksichtigt. Im folgenden Beispiel wird veranschaulicht, wie die Breite und Höhe einer Schaltfläche mit <xref:System.Windows.SystemParameters>\-Werten festgelegt wird.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## Siehe auch  
 <xref:System.Windows.SystemParameters>   
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Verwenden von SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [Verwenden von Systemparameterschlüsseln](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)