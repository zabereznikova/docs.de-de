---
title: "Gewusst wie: Animieren einer Matrix mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Matrixeigenschaften mit Keyframes"
  - "Keyframes, Animieren von Matrixeigenschaften mit"
  - "Matrixeigenschaften, Animieren mit Keyframes"
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Animieren einer Matrix mithilfe von Keyframes
In diesem Beispiel wird die Animation der <xref:System.Windows.Media.MatrixTransform.Matrix%2A>\-Eigenschaft einer <xref:System.Windows.Media.MatrixTransform> mithilfe von Keyframes veranschaulicht.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.Media.MatrixTransform.Matrix%2A>\-Eigenschaft eines <xref:System.Windows.Media.MatrixTransform>\-Elements zu animieren.  Es wird das <xref:System.Windows.Media.MatrixTransform>\-Objekt verwendet, um das Aussehen und die Position eines <xref:System.Windows.Controls.Button>\-Steuerelements zu transformieren.  
  
 Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>\-Klasse, um zwei Keyframes zu erstellen, und behandelt die Keyframes dann wie folgt:  
  
1.  Animiert während der ersten 0,2 Sekunden die erste <xref:System.Windows.Media.Matrix>.  Im Beispiel werden die Eigenschaften <xref:System.Windows.Media.Matrix.M11%2A> und <xref:System.Windows.Media.Matrix.M12%2A> der <xref:System.Windows.Media.Matrix> geändert.  Diese Änderung bewirkt, dass sich die Schaltfläche streckt und dass sie verzerrt wird.  Im Beispiel werden außerdem die Eigenschaften <xref:System.Windows.Media.Matrix.OffsetX%2A> und <xref:System.Windows.Media.Matrix.OffsetY%2A> geändert, um die Position der Schaltfläche zu ändern.  
  
2.  Animiert bei 1,0 Sekunden die zweite <xref:System.Windows.Media.Matrix>.  Die Schaltfläche wird an eine andere Position verschoben, und die Schaltfläche ist nicht mehr verzerrt oder gestreckt.  
  
3.  Wiederholt die Animation ohne zeitliche Begrenzung.  
  
> [!NOTE]
>  Keyframes, die vom <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>\-Objekt abgeleitet sind, führen zu plötzlichen Sprüngen zwischen verschiedenen Werten. Die Ausführung der Animation erfolgt also ruckartig.  
  
 [!code-xml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>   
 <xref:System.Windows.Media.MatrixTransform>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)