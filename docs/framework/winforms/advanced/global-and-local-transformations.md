---
title: Globale und lokale Transformationen
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
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e8d05bd0c3e76d643d56b652c8849eef1045ea8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="global-and-local-transformations"></a>Globale und lokale Transformationen
Eine globale Transformation ist eine Transformation, die für jedes Element gezeichnet gilt eine bestimmte <xref:System.Drawing.Graphics> Objekt. Im Gegensatz dazu ist eine lokale Transformation eine Transformation wendet auf ein bestimmtes Element gezeichnet werden.  
  
## <a name="global-transformations"></a>Globale Transformationen  
 Um eine globale Transformation zu erstellen, erstellen eine <xref:System.Drawing.Graphics> Objekt aus, und bearbeiten dann seine <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft. Die <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft ist ein <xref:System.Drawing.Drawing2D.Matrix> Objekt, damit es eine beliebige Sequenz von affine Transformationen aufnehmen kann. Die Transformation gespeichert, der <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft wird die globale Transformation aufgerufen. Die <xref:System.Drawing.Graphics> -Klasse stellt mehrere Methoden für die Erstellung von einer zusammengesetzten globalen Transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, und <xref:System.Drawing.Graphics.TranslateTransform%2A>. Im folgende Beispiel zeichnet eine Ellipse zweimal: einmal vor dem Erstellen einer globalen Transformation und einmal nach. Die Transformation zuerst mit einem Faktor von 0,5 in y-Richtung skaliert und dann 50 Einheiten entlang der x-Achse an übersetzt und dann 30 Grad gedreht.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 Die folgende Abbildung gibt Aufschluss über die Matrizen in der Transformation.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  Im vorherigen Beispiel ist die Ellipse den Ursprung des Koordinatensystems, gedreht auf der linken oberen Ecke des Clientbereichs. Hierdurch wird ein anderes Ergebnis als die Ellipse um ihren Mittelpunkt drehen.  
  
## <a name="local-transformations"></a>Lokale Transformationen  
 Eine lokale Transformation gilt für ein bestimmtes Element gezeichnet werden. Z. B. eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt verfügt über eine <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> Methode, die Ihnen ermöglicht, die Datenpunkten der, dass der Pfad zu transformieren. Im folgende Beispiel zeichnet ein Rechteck mit keine Transformation und einen Pfad mit eine Drehtransformation an. (Wird davon ausgegangen Sie, dass keine globalen Transformation vorhanden ist.)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Sie können die globale Transformation mit lokalen Transformationen, um eine Vielzahl von Ergebnisse zu erzielen kombinieren. Beispielsweise können Sie die globale Transformation für das Koordinatensystem überarbeiten und lokale Transformationen zum Drehen und Skalieren von Objekten, die auf das neue Koordinatensystem gezeichnet verwenden.  
  
 Angenommen Sie, Sie einem Koordinatensystem möchten, die seine Ursprung 200 Pixel vom linken Rand des Clientbereichs und 150 Pixel vom oberen Rand des Clientbereichs verfügt. Darüber hinaus wird davon ausgegangen Sie, dass das Pixel, mit der x-Achse nach rechts und die y-Achse nach oben zeigen als Maßeinheit verwendet werden soll. Das Standard-Koordinatensystem ist die y-Achse nach unten, zeigen, sodass Sie eine Spiegelung entlang der horizontalen Achse durchführen müssen. Die folgende Abbildung zeigt die Matrix für eine solche Spiegelung.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 Als Nächstes wird davon ausgegangen Sie, dass Sie eine 200 Übersetzungseinheiten rechts und 150 Einheiten nach unten durchführen müssen.  
  
 Im folgende Beispiel wird das Koordinatensystem, die eben beschriebene durch die globale Transformation für das Festlegen einer <xref:System.Drawing.Graphics> Objekt.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Der folgende Code (am Ende des vorherigen Beispiels platziert) erstellt einen Pfad, der ein einzelnes Rechteck mit der linken unteren Ecke an den Ursprung des Koordinatensystems an die neue besteht. Das Rechteck wird einmal ohne lokale Transformation und einmal mit lokaler Transformation gefüllt. Die lokale Transformation besteht eine horizontale Skalierung mit einem Faktor von 2 gefolgt von einer 30 Grad drehen.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 Die folgende Abbildung zeigt das neue Koordinatensystem und den zwei Rechtecken.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Siehe auch  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Verwenden von Transformationen in Managed GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
