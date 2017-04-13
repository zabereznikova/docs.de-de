---
title: "Gewusst wie: Animieren in einem Stil | Microsoft Docs"
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
  - "Animation, Eigenschaften, In Formaten"
  - "Formate, Animieren von Eigenschaften in"
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Animieren in einem Stil
Dieses Beispiel zeigt, wie Sie Eigenschaften in einem Stil animieren.  Beim Animieren in einem Stil kann nur das Frameworkelement, für das der Stil definiert ist, direkt als Ziel aufgerufen werden.  Um ein Freezable\-Objekt als Ziel aufzurufen, müssen Sie ausgehend von einer Eigenschaft des formatierten Elements schrittweise darauf zugreifen.  
  
 Im folgenden Beispiel werden mehrere Animationen in einem Stil definiert und einem <xref:System.Windows.Controls.Button> zugewiesen.  Wenn der Benutzer die Maus über die Schaltfläche bewegt, ändert sich die Durchlässigkeit wiederholt von deckend in teilweise transparent und zurück.  Wenn der Benutzer die Maus von der Schaltfläche wegbewegt, wird die volle Deckkraft wiederhergestellt.  Wenn auf die Schaltfläche geklickt wird, ändert sich die Hintergrundfarbe von Orange in Weiß und wieder zurück.  Da der für die Farbgebung der Schaltfläche verwendete <xref:System.Windows.Media.SolidColorBrush> nicht direkt als Ziel aufgerufen werden kann, wird ausgehend von der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft der Schaltfläche schrittweise darauf zugegriffen.  
  
## Beispiel  
 [!code-xml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Beachten Sie, dass beim Animieren in Stilen die Möglichkeit besteht, Objekte als Ziel aufzurufen, die nicht vorhanden sind.  Nehmen Sie an, der Stil verwendet einen <xref:System.Windows.Media.SolidColorBrush>, um die Background\-Eigenschaft einer Schaltfläche festzulegen, an einem Punkt wird der Stil jedoch überschrieben, und der Hintergrund der Schaltfläche wird mit einem <xref:System.Windows.Media.LinearGradientBrush> festgelegt.  Wenn Sie versuchen, den <xref:System.Windows.Media.SolidColorBrush> zu animieren, wird keine Ausnahme ausgelöst, die Animation schlägt ohne Benachrichtigung fehl.  
  
 Weitere Informationen über Syntax zum Aufrufen von Zielen bei Storyboards finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  Weitere Informationen zur Animation finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).