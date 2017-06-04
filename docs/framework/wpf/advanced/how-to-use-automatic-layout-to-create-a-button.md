---
title: "Gewusst wie: Verwenden des automatischen Layouts zum Erstellen einer Schaltfl&#228;che | Microsoft Docs"
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
  - "Automatisches Layout, Erstellen von Schaltflächen"
  - "Button-Steuerelemente, Erstellen mit automatischem Layout"
  - "Erstellen, Schaltflächen mit automatischem Layout"
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Verwenden des automatischen Layouts zum Erstellen einer Schaltfl&#228;che
In diesem Beispiel wird beschrieben, wie der Ansatz für ein automatisches Layout verwendet wird, um eine Schaltfläche in einer lokalisierbaren Anwendung zu erstellen.  
  
 Die Lokalisierung einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann sehr viel Zeit in Anspruch nehmen.  Neben der Übersetzung von Text müssen Lokalisierer häufig die Größe von Elementen ändern und sie neu positionieren.  In der Vergangenheit musste jede Sprache, für die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellt wurde, angepasst werden.  Mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie jetzt Elemente entwerfen, die den Anpassungsaufwand reduzieren.  Der Ansatz, Anwendungen zu schreiben, bei denen Größenänderungen und Neupositionierungen einfacher ausgeführt werden können, wird als `automatic layout` bezeichnet.  
  
 Die folgenden zwei [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispiele erstellen Anwendungen, die eine Schaltfläche instanziieren, eine mit englischem und eine mit spanischem Text.  Beachten Sie, dass der Code mit Ausnahme des Texts übereinstimmt. Die Schaltfläche wird an den Text angepasst.  
  
## Beispiel  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe der Codebeispiele.  
  
 ![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Automatische Anpassung der Schaltflächengröße  
  
## Siehe auch  
 [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Verwenden eines Rasters für automatisches Layout](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)