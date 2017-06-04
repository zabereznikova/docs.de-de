---
title: "Gewusst wie: Animieren der Durchl&#228;ssigkeit eines Elements oder eines Pinsels | Microsoft Docs"
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
  - "Animation, Opacity-Eigenschaft"
  - "Durchlässigkeit, Animation"
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Animieren der Durchl&#228;ssigkeit eines Elements oder eines Pinsels
Um ein Frameworkelement ein\- und auszublenden, können Sie seine <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft animieren. Oder Sie animieren die <xref:System.Windows.Media.Brush.Opacity%2A>\-Eigenschaft des zum Zeichnen des Elements verwendeten <xref:System.Windows.Media.Brush> \(oder der Pinsel\).  Indem Sie die Durchlässigkeit des Elements animieren, blenden Sie das Element und die zugehörigen untergeordneten Elemente ein und aus. Wenn Sie jedoch den zum Zeichnen des Elements verwendeten Pinsel animieren, haben Sie die Möglichkeit, detailliert festzulegen, welche Teile des Elements ein\- und ausgeblendet werden sollen.  Sie können z. B. die Durchlässigkeit des Pinsels animieren, der zum Zeichnen des Hintergrunds einer Schaltfläche verwendet wird.  Dadurch wird der Hintergrund der Schaltfläche ein\- und ausgeblendet, während die Deckkraft des Text voll erhalten bleibt.  
  
> [!NOTE]
>  Die Animierung der <xref:System.Windows.Media.Brush.Opacity%2A> eines <xref:System.Windows.Media.Brush> bietet Leistungsvorteile gegenüber der Animierung der <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft eines Elements.  
  
 Im folgenden Beispiel werden zwei Schaltflächen animiert, um sie ein\- und auszublenden.  Die Durchlässigkeit der ersten <xref:System.Windows.Controls.Button> wird über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden von `1.0` auf `0.0` geändert.  Die zweite Schaltfläche wird ebenfalls animiert, in diesem Fall wird jedoch die Durchlässigkeit des Pinsels geändert, mit dem der <xref:System.Windows.Controls.Control.Background%2A> gezeichnet wird.  Bei Ausführung des Beispiels sehen Sie, dass die erste Schaltfläche vollständig ein\- und ausgeblendet wird, während bei der zweiten Schaltfläche nur der Hintergrund ein\- und ausgeblendet wird.  Text und Rahmen bleiben vollständig sichtbar.  
  
## Beispiel  
 [!code-xml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Der Code wurde in diesem Beispiel weggelassen.  Das vollständige Beispiel zeigt außerdem, wie die Durchlässigkeit einer <xref:System.Windows.Media.Color> in einem <xref:System.Windows.Media.LinearGradientBrush> animiert wird.  Das vollständige Beispiel finden Sie unter [Beispiel für das Animieren von Opacity eines Elements](http://go.microsoft.com/fwlink/?LinkID=159968).