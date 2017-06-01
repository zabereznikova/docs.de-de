---
title: "Gewusst wie: Drehen eines Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Grafiken, Drehen von Objekten"
  - "Drehen von Objekten"
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Drehen eines Objekts
Dieses Beispiel zeigt, wie ein Objekt gedreht wird.  Im Beispiel wird zuerst ein <xref:System.Windows.Media.RotateTransform> erstellt und dann dessen <xref:System.Windows.Media.RotateTransform.Angle%2A> in Grad angegeben.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Shapes.Polyline>\-Objekt um 45 Grad um seine linke obere Ecke gedreht.  
  
## Beispiel  
 [!code-xml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> von <xref:System.Windows.Media.RotateTransform> geben den Punkt an, um den das Objekt gedreht wird.  Dieser Mittelpunkt wird im Koordinatenraum des Elements ausgedrückt, das transformiert wird.  Standardmäßig wird die Drehung um den Punkt \(0,0\), die obere linke Ecke des zu transformierenden Objekts, vorgenommen.  
  
 Im nächsten Beispiel wird ein <xref:System.Windows.Shapes.Polyline>\-Objekt um 45 Grad im Uhrzeigersinn um den Punkt \(25,50\) gedreht.  
  
 [!code-xml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 In der folgenden Abbildung werden die Ergebnisse der Anwendung von <xref:System.Windows.Media.Transform> auf die beiden Objekte dargestellt.  
  
 ![45&#45;Grad&#45;Drehungen mit unterschiedlichen Mittelpunkten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
Zwei Objekte, die um unterschiedliche Drehpunkte um 45 Grad gedreht werden  
  
 Das <xref:System.Windows.Shapes.Polyline>\-Objekt in den vorherigen Beispielen ist ein <xref:System.Windows.UIElement>.  Wenn Sie ein <xref:System.Windows.Media.Transform>\-Objekt auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft eines <xref:System.Windows.UIElement>\-Objekts anwenden, können Sie mithilfe der <xref:System.Windows.UIElement.RenderTransformOrigin%2A>\-Eigenschaft einen Ursprung für jedes <xref:System.Windows.Media.Transform>\-Objekt angeben, das Sie auf das Element anwenden.  Da für die <xref:System.Windows.UIElement.RenderTransformOrigin%2A>\-Eigenschaft relative Koordinaten verwendet werden, können Sie auch dann eine Transformation auf den Mittelpunkt des Elements anwenden, wenn Sie dessen Größe nicht kennen.  Weitere Informationen und ein Beispiel finden Sie unter [Angeben des Ursprungs einer Transformation mithilfe von relativen Werten](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Das vollständige Beispiel finden Sie unter [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Siehe auch  
 <xref:System.Windows.Media.Transform>   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)