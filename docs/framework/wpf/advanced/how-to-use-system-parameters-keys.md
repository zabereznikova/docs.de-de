---
title: "Gewusst wie: Verwenden von Systemparameterschl&#252;sseln | Microsoft Docs"
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
  - "Ressourcenschlüssel, SystemParameters-Klasse"
  - "SystemParameters-Klasse"
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Verwenden von Systemparameterschl&#252;sseln
Systemressourcen machen verschiedene Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Objekte erstellen können, die den Systemeinstellungen entsprechen.  <xref:System.Windows.SystemParameters> ist eine Klasse, die sowohl Systemparameterwerte als auch Ressourcenschlüssel enthält, die an die Werte gebunden werden. Dazu zählen <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.  Systemparametermetriken können entweder als statische oder als dynamische Ressourcen verwendet werden.  Wenn die Parametermetrik beim Ausführen der Anwendung automatisch aktualisiert werden soll, verwenden Sie eine dynamische Ressource; andernfalls verwenden Sie eine statische Ressource.  
  
> [!NOTE]
>  Bei dynamischen Ressourcen ist das Schlüsselwort *Key* an den Eigenschaftennamen angefügt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie auf dynamische Ressourcen der Systemparameter zugegriffen werden kann und wie sie sich verwenden lassen, um eine Schaltfläche zu formatieren oder anzupassen.  In diesem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Beispiel wird die Größe einer Schaltfläche angepasst, indem <xref:System.Windows.SystemParameters>\-Werte der Breite und der Höhe der Schaltfläche zugewiesen werden.  
  
## Beispiel  
 [!code-xml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## Siehe auch  
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Verwenden von SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [Verwenden von SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)