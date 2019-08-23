---
title: Globale und lokale Transformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955189"
---
# <a name="global-and-local-transformations"></a>Globale und lokale Transformationen
Eine globale Transformation ist eine Transformation, die auf jedes Element angewendet wird, das <xref:System.Drawing.Graphics> von einem bestimmten Objekt gezeichnet wird. Im Gegensatz dazu ist eine lokale Transformation eine Transformation, die auf ein bestimmtes Element angewendet wird, das gezeichnet werden soll.  
  
## <a name="global-transformations"></a>Globale Transformationen  
 Um eine globale Transformation zu erstellen, erstellen <xref:System.Drawing.Graphics> Sie ein-Objekt, und <xref:System.Drawing.Graphics.Transform%2A> bearbeiten Sie dann die zugehörige-Eigenschaft. Die <xref:System.Drawing.Graphics.Transform%2A> -Eigenschaft ist <xref:System.Drawing.Drawing2D.Matrix> ein-Objekt, sodass Sie eine beliebige Sequenz von affinen Transformationen enthalten kann. Die in der <xref:System.Drawing.Graphics.Transform%2A> -Eigenschaft gespeicherte Transformation wird als weltweite Transformation bezeichnet. Die <xref:System.Drawing.Graphics> -Klasse stellt mehrere Methoden zum Aufbauen einer zusammengesetzten Welt Transformation <xref:System.Drawing.Graphics.MultiplyTransform%2A>bereit <xref:System.Drawing.Graphics.RotateTransform%2A>: <xref:System.Drawing.Graphics.ScaleTransform%2A>,, <xref:System.Drawing.Graphics.TranslateTransform%2A>und. Im folgenden Beispiel wird eine Ellipse zweimal gezeichnet: einmal vor dem Erstellen einer Welt Transformation und einmal nach. Die Transformation skaliert zuerst mit dem Faktor 0,5 in der y-Richtung, übersetzt dann 50 Einheiten in die x-Richtung und dreht dann 30 Grad.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 Die folgende Abbildung zeigt die Matrizen, die an der Transformation beteiligt sind.  
  
 ![Transformationen](./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
> Im vorherigen Beispiel wird die Ellipse um den Ursprung des Koordinatensystems gedreht, das sich in der oberen linken Ecke des Client Bereichs befindet. Dies führt zu einem anderen Ergebnis als das Drehen der Ellipse über einen eigenen Mittelpunkt.  
  
## <a name="local-transformations"></a>Lokale Transformationen  
 Eine lokale Transformation gilt für ein bestimmtes Element, das gezeichnet werden soll. Ein <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt verfügt beispielsweise über <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> eine-Methode, die es Ihnen ermöglicht, die Datenpunkte dieses Pfades zu transformieren. Im folgenden Beispiel wird ein Rechteck ohne Transformation und ein Pfad mit einer Rotations Transformation gezeichnet. (Angenommen, es gibt keine Welt Transformation.)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Sie können die Welt Transformation mit lokalen Transformationen kombinieren, um eine Vielzahl von Ergebnissen zu erzielen. Beispielsweise können Sie mit der Welt Transformation das Koordinatensystem überarbeiten und lokale Transformationen verwenden, um Objekte zu drehen und zu skalieren, die auf dem neuen Koordinatensystem gezeichnet werden.  
  
 Angenommen, Sie möchten ein Koordinatensystem, dessen Ursprung 200 Pixel vom linken Rand des Client Bereichs und 150 Pixel vom oberen Rand des Client Bereichs hat. Angenommen, Sie möchten, dass die Maßeinheit das Pixel ist, wobei die x-Achse nach rechts und die y-Achse nach oben zeigt. Beim Standard Koordinatensystem wird die y-Achse nach unten angezeigt, sodass Sie eine Reflektion auf der horizontalen Achse ausführen müssen. Die folgende Abbildung zeigt die Matrix einer solchen Reflektion.  
  
 ![Transformationen](./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 Nehmen wir als nächstes an, dass Sie eine Translation 200-Einheiten nach rechts und 150-Einheiten ausführen müssen.  
  
 Im folgenden Beispiel wird das Koordinatensystem festgelegt, das gerade durch Festlegen der Welt <xref:System.Drawing.Graphics> Transformation eines-Objekts beschrieben wird.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Der folgende Code (am Ende des vorangehenden Beispiels eingefügt) erstellt einen Pfad, der aus einem einzelnen Rechteck mit der unteren linken Ecke am Ursprung des neuen Koordinatensystems besteht. Das Rechteck wird einmal ohne lokale Transformation und einmal mit einer lokalen Transformation aufgefüllt. Die lokale Transformation besteht aus einer horizontalen Skalierung mit dem Faktor 2, gefolgt von einer 30-Grad-Drehung.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 Die folgende Abbildung zeigt das neue Koordinatensystem und die beiden Rechtecke.  
  
 ![Transformationen](./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Siehe auch

- [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md)
- [Verwenden von Transformationen in Managed GDI+](using-transformations-in-managed-gdi.md)
