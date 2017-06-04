---
title: "Typen von Koordinatensystemen | Microsoft Docs"
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
  - "Koordinatensysteme"
  - "Gerätekoordinatensystem"
  - "Seitenkoordinatensystem"
  - "Seitentransformation"
  - "Transformationen, Seite"
  - "Transformationen, Global"
  - "Maßeinheit"
  - "Globales Koordinatensystem"
  - "Globale Transformation"
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Typen von Koordinatensystemen
In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] werden drei Koordinatensysteme verwendet: Global, Seite und Gerät.  Globale Koordinaten sind Koordinaten zum Entwurf einer bestimmten Grafikumgebung und werden an Methoden in .NET Framework übergeben.  Seitenkoordinaten beziehen sich auf das von einer Zeichnungsoberfläche, z. B. einem Formular oder Steuerelement, verwendete Koordinatensystem.  Gerätekoordinaten sind die von einem physikalischen Zeichengerät, z. B. einem Bildschirm oder Blatt Papier, verwendeten Koordinaten.  Wenn Sie den Aufruf `myGraphics.DrawLine(myPen, 0, 0, 160, 80)` ausführen, befinden sich die an die <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode übergebenen Punkte – `(0, 0)` und `(160, 80)` – im globalen Koordinatensystem.  Bevor [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] die Linie auf dem Bildschirm zeichnen kann, durchlaufen die Koordinaten eine Sequenz von Transformationen.  Durch eine Transformation, die so genannte globale Transformation, werden globale Koordinaten in Seitenkoordinaten konvertiert, und durch eine andere Transformation, die so genannte Seitentransformation, werden Seitenkoordinaten in Gerätekoordinaten konvertiert.  
  
## Transformationen und Koordinatensysteme  
 Angenommen, Sie möchten ein Koordinatensystem verwenden, dessen Ursprung sich innerhalb des Clientbereichs befindet und nicht in der linken oberen Ecke.  Nehmen wir außerdem an, der Ursprung soll 100 Pixel vom linken Rand des Clientbereichs entfernt und 50 Pixel vom oberen Rand des Clientbereichs entfernt liegen.  Die folgende Abbildung zeigt ein solches Koordinatensystem.  
  
 ![Koordinatensystem](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.png "AboutGdip05\_art01")  
  
 Wenn Sie den Aufruf `myGraphics.DrawLine(myPen, 0, 0, 160, 80)` ausführen, wird die in der folgenden Abbildung dargestellte Linie ausgegeben.  
  
 ![Koordinatensystem](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.png "AboutGdip05\_art02")  
  
 Die Koordinaten der Endpunkte der Linie lauten in den drei Koordinatensystemen wie folgt:  
  
|||  
|-|-|  
|World|\(0; 0\) bis \(160; 80\)|  
|Seite|\(100; 50\) bis \(260; 130\)|  
|Gerät|\(100; 50\) bis \(260; 130\)|  
  
 Beachten Sie, dass der Ursprung des Seitenkoordinatensystems in der linken oberen Ecke des Clientbereichs liegt. Dies ist immer der Fall.  Beachten Sie außerdem, dass die Gerätekoordinaten die gleichen sind wie die Seitenkoordinaten, da die Maßeinheit Pixel lautet.  Wenn Sie die Maßeinheit ändern \(z. B. auf Zoll\), weichen die Gerätekoordinaten von den Seitenkoordinaten ab.  
  
 Die globale Transformation, bei der eine Zuordnung von globalen Koordinaten und Seitenkoordinaten stattfindet, wird in der <xref:System.Drawing.Graphics.Transform%2A>\-Eigenschaft der <xref:System.Drawing.Graphics>\-Klasse gespeichert.  Im obigen Beispiel ist die globale Transformation eine Verschiebung um 100 Einheiten in x‑Richtung und 50 Einheiten in y‑Richtung.  Im folgenden Beispiel wird die globale Transformation eines <xref:System.Drawing.Graphics>\-Objekts festgelegt und dann mithilfe dieses <xref:System.Drawing.Graphics>\-Objekts die in der obigen Abbildung dargestellte Linie gezeichnet:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 Bei der Seitentransformation findet eine Zuordnung von Seiten\- und Gerätekoordinaten statt.  Die <xref:System.Drawing.Graphics>\-Klasse stellt die Eigenschaften <xref:System.Drawing.Graphics.PageUnit%2A> und <xref:System.Drawing.Graphics.PageScale%2A> zum Bearbeiten der Seitentransformation bereit.  Die <xref:System.Drawing.Graphics>\-Klasse stellt außerdem die beiden schreibgeschützten Eigenschaften <xref:System.Drawing.Graphics.DpiX%2A> und <xref:System.Drawing.Graphics.DpiY%2A> bereit, mit denen der horizontale und vertikale dpi\-Wert \(Punkte pro Zoll\) des Anzeigegeräts untersucht wird.  
  
 Sie können mithilfe der <xref:System.Drawing.Graphics.PageUnit%2A>\-Eigenschaft der <xref:System.Drawing.Graphics>\-Klasse eine andere Maßeinheit als Pixel angeben.  
  
> [!NOTE]
>  Die <xref:System.Drawing.Graphics.PageUnit%2A>\-Eigenschaft kann nicht auf <xref:System.Drawing.GraphicsUnit> festgelegt werden, da dies keine physische Komponente ist und daher eine Ausnahme ausgelöst würde.  
  
 Im folgenden Beispiel wird eine Linie von \(0, 0\) nach \(2, 1\) gezogen, wobei der Punkt \(2, 1\) 2 Zoll rechts vom Punkt \(0, 0\) und 1 Zoll darunter liegt:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  Wenn Sie beim Erstellen des Stiftes keine Stiftbreite angeben, wird im obigen Beispiel eine Linie mit einer Breite von 1 Zoll gezeichnet.  Sie können die Stiftbreite im zweiten Argument für den <xref:System.Drawing.Pen>\-Konstruktor angeben:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Unter der Annahme, dass das Anzeigegerät 96 Punkte pro Zoll in horizontaler Richtung und 96 Punkte pro Zoll in vertikaler Richtung anzeigt, haben die Endpunkte der Linie im obigen Beispiel in den drei Koordinatensystemen die folgenden Koordinaten:  
  
|||  
|-|-|  
|World|\(0; 0\) bis \(2; 1\)|  
|Seite|\(0; 0\) bis \(2; 1\)|  
|Gerät|\(0, 0\) bis \(192, 96\)|  
  
 Da sich der Ursprung des globalen Koordinatensystems in der linken oberen Ecke des Clientbereichs befindet, sind die Seitenkoordinaten mit den globalen Koordinaten identisch.  
  
 Sie können die globale Transformation und die Seitentransformation kombinieren, um verschiedenste Effekte zu erzielen.  Nehmen wir beispielsweise an, Sie möchten als Maßeinheit Zoll verwenden, und der Ursprung des Koordinatensystems soll 2 Zoll vom linken Rand des Clientbereichs und 1\/2 Zoll vom oberen Rand des Clientbereichs entfernt liegen.  Im folgenden Beispiel wird die globale Transformation und die Seitentransformation eines <xref:System.Drawing.Graphics>\-Objekts festgelegt und anschließend eine Linie von \(0, 0\) nach \(2, 1\) gezogen:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 Die folgende Abbildung zeigt die Linie und das Koordinatensystem.  
  
 ![Koordinatensystem](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.png "AboutGdip05\_art03")  
  
 Unter der Annahme, dass das Anzeigegerät 96 Punkte pro Zoll in horizontaler Richtung und 96 Punkte pro Zoll in vertikaler Richtung anzeigt, haben die Endpunkte der Linie im obigen Beispiel in den drei Koordinatensystemen die folgenden Koordinaten:  
  
|||  
|-|-|  
|World|\(0; 0\) bis \(2; 1\)|  
|Seite|\(2; 0,5\) bis \(4; 1,5\)|  
|Gerät|\(192; 48\) bis \(384; 144\)|  
  
## Siehe auch  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Matrixdarstellung von Transformationen](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)