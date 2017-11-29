---
title: Typen von Koordinatensystemen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be89584ee8e7a82c405bf8664bfad18ced6d989a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-coordinate-systems"></a>Typen von Koordinatensystemen
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]verwendet drei Koordinatensysteme: Global, Seite und Gerät. Globalen Koordinaten sind die Koordinaten verwendet, um eine bestimmte Grafik World modellieren und die Koordinaten, die Sie an Methoden in .NET Framework zu übergeben. Seitenkoordinaten beziehen sich auf das Koordinatensystem, die von einer Zeichenoberfläche, z. B. eines Formulars oder Steuerelements verwendet. Gerätekoordinaten sind die Koordinaten, die durch das physische Gerät, z. B. einem Bildschirm oder Blatt Papier gezeichnet werden verwendet. Stellen Sie, wenn den Aufruf `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, die Punkte, die Sie zum Übergeben der <xref:System.Drawing.Graphics.DrawLine%2A> Methode –`(0, 0)` und `(160, 80)`– befinden sich in der ganzen Welt Koordinatenbereich. Vor dem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können die Linie auf dem Bildschirm, durchlaufen die Koordinaten auf eine Sequenz von Transformationen. Eine Transformation, die die globale Transformation aufgerufen globalen Koordinaten Seitenkoordinaten konvertiert und eine andere Transformation, die Seitentransformation aufgerufen konvertiert Seitenkoordinaten in logische Koordinaten.  
  
## <a name="transforms-and-coordinate-systems"></a>Transformationen und Koordinatensysteme  
 Angenommen Sie, Sie arbeiten mit einem Koordinatensystem, die seinen Ursprung im Text des Clientbereichs statt in der oberen linken Ecke hat möchten. Nehmen Sie z. B., den Ursprung 100 Pixel vom linken Rand des Clientbereichs und 50 Pixel vom oberen Rand des Clientbereichs sein soll. Die folgende Abbildung zeigt eine solche einem Koordinatensystem.  
  
 ![Koordinatensystem](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Stellen Sie, wenn den Aufruf `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, erhalten Sie die Zeile in der folgenden Abbildung gezeigt.  
  
 ![Koordinatensystem](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Die Koordinaten der Endpunkte der Linie in den drei Koordinatensystemen lauten wie folgt:  
  
|||  
|-|-|  
|World|(0, 0), (160, 80)|  
|Seite|(100, 50), (260, 130)|  
|Gerät|(100, 50), (260, 130)|  
  
 Beachten Sie, dass die Seite Koordinatenbereich auf der linken oberen Ecke des Clientbereichs Ursprungssite verfügt; Dies wird immer der Fall sein. Beachten Sie außerdem, da die Maßeinheit Pixel ist, die Gerätekoordinaten der Seitenkoordinaten identisch sind. Wenn Sie die Maßeinheit auf einen anderen Wert als Pixel (z. B. Zoll) festlegen, werden die Gerätekoordinaten mit den Seitenkoordinaten abweichen.  
  
 Die globale Transformation, die globalen Koordinaten Seitenkoordinaten zuordnet, gehalten wird, der <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft von der <xref:System.Drawing.Graphics> Klasse. Im vorherigen Beispiel wird die globale Transformation 100 Übersetzungseinheiten in X-Richtung und 50 Einheiten entlang der y-Achse an. Im folgenden Beispiel wird die globale Transformation für eine <xref:System.Drawing.Graphics> Objekt, und klicken Sie dann verwendet, die <xref:System.Drawing.Graphics> Objekt zum Zeichnen der Linie, die in der obigen Abbildung gezeigt:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 Die Seitentransformation ordnet Seitenkoordinaten Gerätekoordinaten. Die <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.PageUnit%2A> und <xref:System.Drawing.Graphics.PageScale%2A> Eigenschaften zum Bearbeiten der Seitentransformation. Die <xref:System.Drawing.Graphics> Klasse bietet auch zwei schreibgeschützte Eigenschaften <xref:System.Drawing.Graphics.DpiX%2A> und <xref:System.Drawing.Graphics.DpiY%2A>, untersuchen Sie die horizontalen und vertikalen Punkte pro Zoll des Geräts angezeigt.  
  
 Können Sie die <xref:System.Drawing.Graphics.PageUnit%2A> Eigenschaft von der <xref:System.Drawing.Graphics> Klasse, um eine Maßeinheit als Pixel anzugeben.  
  
> [!NOTE]
>  Kann nicht festgelegt werden die <xref:System.Drawing.Graphics.PageUnit%2A> Eigenschaft <xref:System.Drawing.GraphicsUnit.World>, wie dies eine physische fehlereinheit ist und wird eine Ausnahme ausgelöst.  
  
 Im folgende Beispiel zeichnet eine verbindende Linie aus (0, 0), (2, 1), in dem der Punkt (2, 1) 2 Zoll rechts und 1 Zoll nach unten ab dem Punkt (0, 0) ist:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  Wenn Sie beim Erstellen des Stifts eine Breite nicht angeben, wird im vorherige Beispiel eine Linie gezeichnet, die einen Zoll breit ist. Sie können die Stiftbreite angeben, in das zweite Argument der <xref:System.Drawing.Pen> Konstruktor:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Wenn Sie davon ausgehen, dass die Anzeigegerät 96 dpi in horizontaler Richtung und 96 dpi in vertikaler Richtung aufweist, sind die Endpunkte der Linie im vorherigen Beispiel folgenden Koordinaten in drei Koordinatensysteme:  
  
|||  
|-|-|  
|World|(0, 0), (2, 1)|  
|Seite|(0, 0), (2, 1)|  
|Gerät|(0, 0 (null), (192, 96)|  
  
 Beachten Sie, dass da des Ursprungs von der ganzen Welt Koordinatenbereich auf der linken oberen Ecke des Clientbereichs ist, die Seitenkoordinaten mit den globalen Koordinaten identisch sind.  
  
 Sie können die World Transformation und der Seitentransformation um eine Vielzahl von Effekte erzielen kombinieren. Nehmen wir beispielsweise an Zoll als Maßeinheit verwendet werden sollen, und den Ursprung des Koordinatensystems vom linken Rand des Clientbereichs und 1/2-Zoll vom oberen Rand des Clientbereichs von 2 Zoll sein sollen. Im folgenden Beispiel wird die World Transformation und der Seitentransformation ein <xref:System.Drawing.Graphics> Objekt, und klicken Sie dann zeichnet eine verbindende Linie aus (0, 0), (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 Die folgende Abbildung zeigt die Zeile und das Koordinatensystem.  
  
 ![Koordinatensystem](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Wenn Sie davon ausgehen, dass die Anzeigegerät 96 dpi in horizontaler Richtung und 96 dpi in vertikaler Richtung aufweist, sind die Endpunkte der Linie im vorherigen Beispiel folgenden Koordinaten in drei Koordinatensysteme:  
  
|||  
|-|-|  
|World|(0, 0), (2, 1)|  
|Seite|(2, 0,5), (4, 1.5)|  
|Gerät|(192, 48) an (384, 144)|  
  
## <a name="see-also"></a>Siehe auch  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Matrixdarstellung von Transformationen](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
