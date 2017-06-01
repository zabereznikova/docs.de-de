---
title: "Globale und lokale Transformationen | Microsoft Docs"
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
  - "Matrizen, Verwenden von Transformationen"
  - "Transformationen, Global"
  - "Transformationen, Lokal"
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Globale und lokale Transformationen
Eine globale Transformation ist eine Transformation, die für jedes Element gilt, das von einem bestimmten <xref:System.Drawing.Graphics>\-Objekt gezeichnet wird.  Eine lokale Transformation ist dagegen eine Transformation, die für ein bestimmtes zu zeichnendes Element gilt.  
  
## Globale Transformationen  
 Um eine globale Transformation zu erstellen, konstruieren Sie ein <xref:System.Drawing.Graphics>\-Objekt und bearbeiten dann dessen <xref:System.Drawing.Graphics.Transform%2A>\-Eigenschaft.  Die <xref:System.Drawing.Graphics.Transform%2A>\-Eigenschaft ist ein <xref:System.Drawing.Drawing2D.Matrix>\-Objekt und kann daher eine beliebige Folge von affinen Transformationen speichern.  Die in der <xref:System.Drawing.Graphics.Transform%2A>\-Eigenschaft gespeicherte Transformation wird als globale Transformation bezeichnet.  Die <xref:System.Drawing.Graphics>\-Klasse stellt mehrere Methoden zum Erstellen einer zusammengesetzten globalen Transformation bereit: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A> und <xref:System.Drawing.Graphics.TranslateTransform%2A>.  Im folgenden Beispiel wird eine Ellipse zweimal gezeichnet: einmal vor dem Erstellen einer globalen Transformation und einmal danach.  Die Transformation führt zuerst eine Skalierung um den Faktor 0,5 in y‑Richtung aus, dann eine Verschiebung um 50 Einheiten in x‑Richtung und anschließend eine Drehung um 30 Grad.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 Die folgende Abbildung zeigt die bei der Transformation verwendeten Matrizen.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05\_art14")  
  
> [!NOTE]
>  Im obigen Beispiel wird die Ellipse um den Ursprung des Koordinatensystems herum gedreht. Dieser befindet sich in der linken oberen Ecke des Clientbereichs.  Dies führt zu einem anderen Ergebnis als das Drehen der Ellipse um ihren Mittelpunkt.  
  
## Lokale Transformationen  
 Eine lokale Transformation gilt für ein bestimmtes zu zeichnendes Element.  Beispielsweise hat ein <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt eine <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A>\-Methode, mit der Sie die Datenpunkte dieses Pfades transformieren können.  Im folgenden Beispiel wird ein Rechteck ohne Transformation und ein Pfad mit einer Drehungstransformation gezeichnet.  \(Eine globale Transformation ist nicht vorhanden.\)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Sie können die globale Transformation mit lokalen Transformationen kombinieren, um verschiedenste Ergebnisse zu erzielen.  Beispielsweise können Sie mithilfe der globalen Transformation das Koordinatensystem ändern und mit lokalen Transformationen Objekte, die in dem neuen Koordinatensystem gezeichnet wurden, drehen und skalieren.  
  
 Angenommen, der Ursprung eines Koordinatensystems soll 200 Pixel vom linken Rand des Clientbereichs entfernt und 150 Pixel vom oberen Rand des Clientbereichs entfernt liegen.  Nehmen wir weiter an, dass Sie Pixel als Maßeinheit verwenden möchten, wobei die x‑Achse nach rechts und die y‑Achse nach oben zeigt.  Beim Standardkoordinatensystem zeigt die y‑Achse nach unten, sodass Sie eine Spiegelung entlang der horizontalen Achse durchführen müssen.  Die folgende Abbildung zeigt die Matrix für eine solche Spiegelung.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.png "AboutGdip05\_art15")  
  
 Nehmen wir als Nächstes an, Sie müssen eine Verschiebung um 200 Einheiten nach rechts und 150 Einheiten nach unten durchführen.  
  
 Im folgenden Beispiel wird das oben beschriebene Koordinatensystem durch Festlegen der globalen Transformation eines <xref:System.Drawing.Graphics>\-Objekts erstellt.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Der folgende Code \(am Ende des vorherigen Beispiels platziert\) erstellt einen Pfad, der aus einem einzigen Rechteck besteht, dessen linke untere Ecke sich im Ursprung des neuen Koordinatensystems befindet.  Das Rechteck wird einmal ohne lokale Transformation und einmal mit lokaler Transformation gefüllt.  Die lokale Transformation umfasst eine horizontale Skalierung um den Faktor 2 und eine Drehung um 30 Grad.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 Die folgende Abbildung zeigt das neue Koordinatensystem und die beiden Rechtecke.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.png "AboutGdip05\_art16")  
  
## Siehe auch  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Verwenden von Transformationen in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)