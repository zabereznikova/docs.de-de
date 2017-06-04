---
title: "Gewusst wie: Verwenden eines Rasters f&#252;r automatisches Layout | Microsoft Docs"
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
  - "Automatisches Layout, Rasterverwendung"
  - "Raster, Automatisches Layout"
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Verwenden eines Rasters f&#252;r automatisches Layout
In diesem Beispiel wird beschrieben, wie ein Raster im automatischen Layoutansatz verwendet wird, um eine lokalisierbare Anwendung zu erstellen.  
  
 Die Lokalisierung einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann sehr viel Zeit in Anspruch nehmen.  Neben der Übersetzung von Text müssen Lokalisierer häufig die Größe von Elementen ändern und sie neu positionieren.  In der Vergangenheit musste jede Sprache, für die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellt wurde, angepasst werden.  Mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie jetzt Elemente entwerfen, die den Anpassungsaufwand reduzieren.  Der Ansatz, Anwendungen zu schreiben, bei denen Größenänderungen und Neupositionierungen einfacher ausgeführt werden können, wird als `auto layout` bezeichnet.  
  
 Im folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispiel wird veranschaulicht, wie mit einem Raster einige Schaltflächen und Text neu positioniert werden.  Beachten Sie, dass Höhe und Breite der Zellen auf `Auto` festgelegt sind. Daher wird die Größe der Zelle, die die Schaltfläche mit einem Bild enthält, an das Bild angepasst.  Da die Größe des <xref:System.Windows.Controls.Grid>\-Elements an seinen Inhalt angepasst werden kann, kann dies beim Verwenden des automatischen Layoutansatzes zum Entwerfen von lokalisierbaren Anwendungen hilfreich sein.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung eines Rasters.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe des Codebeispiels.  
  
 ![Rasterbeispiel](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
Raster  
  
## Siehe auch  
 [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)