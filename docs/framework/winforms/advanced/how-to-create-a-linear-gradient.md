---
title: "Gewusst wie: Erstellen eines linearen Farbverlaufs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Farben, Erstellen linearer Farbverläufe"
  - "Farbverläufe"
  - "Farbverläufe, Erstellen von linearen"
  - "Lineare Farbverläufe, Erstellen"
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Erstellen eines linearen Farbverlaufs
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet horizontale, vertikale und diagonale lineare Farbverläufe.  Die Farbe in einem linearen Farbverlauf wird im Normalfall gleichmäßig geändert.  Sie können einen linearen Farbverlauf jedoch auch anpassen, sodass die Farbe ungleichmäßig geändert wird.  
  
 Im folgenden Beispiel werden eine Linie, eine Ellipse und ein Rechteck mit einem Pinsel mit horizontalem linearem Farbverlauf ausgefüllt.  
  
 Der <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>\-Konstruktor empfängt vier Argumente: zwei Punkte und zwei Farben.  Der erste Punkt \(0, 10\) ist mit der ersten Farbe \(Rot\) und der zweite Punkt \(200, 10\) mit der zweiten Farbe \(Blau\) verknüpft.  Erwartungsgemäß ändert sich die Farbe der Linie, die von \(0, 10\) nach \(200, 10\) gezeichnet wird, graduell von Rot nach Blau.  
  
 Die Werte 10 in den Punkten \(50, 10\) und \(200, 10\) sind nicht wichtig.  Es kommt lediglich darauf an, dass die zweite Koordinate der beiden Punkte identisch ist, die Verbindungslinie also horizontal verläuft.  Auch die Farbe der Ellipse und des Rechtecks ändert sich von Rot nach Blau, wenn die horizontale Koordinate von 0 auf 200 ansteigt.  
  
 In der folgenden Abbildung werden die Linie, die Ellipse und das Rechteck angezeigt.  Beachten Sie, dass der Farbverlauf sich wiederholt, wenn die horizontale Koordinate über den Wert 200 hinausgeht.  
  
 ![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### So verwenden Sie horizontale lineare Farbverläufe  
  
-   Übergeben Sie die nicht transparenten Farben Rot und Blau als drittes bzw. viertes Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 Die Farbkomponenten im vorhergehenden Beispiel verändern sich beim Verschieben der horizontalen Koordinate von 0 auf 200 linear.  Wenn sich beispielsweise ein Punkt genau zwischen 0 und 200 befindet, liegt sein Blauwert genau in der Mitte zwischen 0 und 255.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ermöglicht es Ihnen, die Art des Farbwechsels von einem Ende des Farbverlaufs zum anderen anzupassen.  Angenommen, Sie möchten einen Farbverlaufspinsel erstellen, der entsprechend der folgenden Tabelle von Schwarz in Rot übergeht:  
  
|Horizontale Koordinate|RGB\-Komponenten|  
|----------------------------|----------------------|  
|0|\(0, 0, 0\)|  
|40|\(128, 0, 0\)|  
|200|\(255, 0, 0\)|  
  
 Beachten Sie, dass der Rotanteil bereits die Hälfte der maximalen Intensität hat, wenn die horizontale Koordinate erst 20 Prozent der Strecke von 0 nach 200 entspricht.  
  
 Im folgenden Beispiel wird die <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A>\-Eigenschaft eines <xref:System.Drawing.Drawing2D.LinearGradientBrush>\-Objekts festgelegt, um drei relative Intensitäten mit drei relativen Positionen zu verknüpfen.  Wie in der vorangehenden Tabelle wird die relative Intensität 0.5 mit der relativen Position 0.2 verknüpft.  Durch den Code werden eine Ellipse und ein Rechteck mit dem Farbverlaufspinsel ausgefüllt.  
  
 In der folgenden Abbildung sind die resultierende Ellipse und das resultierende Rechteck dargestellt.  
  
 ![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### So passen Sie lineare Farbverläufe an  
  
-   Übergeben Sie die nicht transparenten Farben Schwarz und Rot als drittes bzw. viertes Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Die Farbverläufe in den bisherigen Beispielen verlaufen in horizontaler Richtung, d. h., die Farbe wechselt graduell entlang einer beliebigen horizontalen Linie.  Darüber hinaus können Sie auch vertikale und diagonale Farbverläufe festlegen.  
  
 Im folgenden Beispiel werden die Punkte \(0, 0\) und \(200, 100\) an einen <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>\-Konstruktor übergeben.  Die Farbe Blau wird mit \(0, 0\) und die Farbe Grün mit \(200, 100\) verknüpft.  Eine Linie \(mit Stiftbreite 10\) und eine Ellipse werden mit dem Pinsel mit linearem Farbverlauf ausgefüllt.  
  
 In der folgenden Abbildung sind die Linie und die Ellipse dargestellt.  Die Farbe in der Ellipse wechselt graduell entlang einer beliebigen Linie, die parallel zu der Linie mit den Punkten \(0, 0\) und \(200, 100\) verläuft.  
  
 ![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### So erstellen Sie diagonale lineare Farbverläufe  
  
-   Übergeben Sie die nicht transparenten Farben Blau und Grün als drittes bzw. viertes Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## Siehe auch  
 [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)