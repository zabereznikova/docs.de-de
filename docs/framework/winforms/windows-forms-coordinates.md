---
title: Windows Forms-Koordinaten
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: a6f082eb57a9cfe1af0d4207cbf5226637191c90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556050"
---
# <a name="windows-forms-coordinates"></a>Windows Forms-Koordinaten
Das Koordinatensystem für eine Windows-Formular auf Gerätekoordinaten basiert, und die grundlegende Maßeinheit beim Zeichnen in Windows Forms ist die Einheit des Geräts (in der Regel die Pixel). Punkte auf dem Bildschirm werden von x- und y-Koordinate-Paare, mit den X-Koordinaten, erhöhen nach rechts und die y-Koordinaten erhöhen von oben nach unten beschrieben. Die Position des Ursprungs, relativ zum Bildschirm, hängen davon ab, ob Sie Bildschirm- oder Clientkoordinaten angeben.  
  
## <a name="screen-coordinates"></a>Bildschirmkoordinaten  
 Eine Windows Forms-Anwendung gibt die Position eines Fensters auf dem Bildschirm in Bildschirmkoordinaten. Für die Bildschirmkoordinaten ist der Ursprung die linke obere Ecke des Bildschirms. Die vollständige Position eines Fensters wird häufig durch beschrieben eine <xref:System.Drawing.Rectangle> -Struktur, enthält die Bildschirmkoordinaten von zwei Punkten, die die linken, oberen und unteren rechten Ecke des Fensters definieren.  
  
## <a name="client-coordinates"></a>Clientkoordinaten  
 Eine Windows Forms-Anwendung gibt die Position der Punkte in einem Formular oder Steuerelement unter Verwendung der Clientkoordinaten. Der Ursprung Clientkoordinaten ist der linke obere Ecke des Clientbereichs des Steuerelements oder Formulars. Clientkoordinaten stellen Sie sicher, dass eine Anwendung in einem Formular oder Steuerelement, unabhängig von der Position des Formulars oder Steuerelements auf dem Bildschirm zeichnen konsistente Koordinatenwerte verwenden kann.  
  
 Darüber hinaus werden die Abmessungen des Clientbereichs beschrieben durch einen <xref:System.Drawing.Rectangle> -Struktur, die Clientkoordinaten für den Bereich enthält. In allen Fällen ist die linke obere Koordinate des Rechtecks im Clientbereich, enthalten, während die untere rechte Koordinate ausgeschlossen ist. Grafikoperationen enthalten nicht den rechten und unteren Rand des Clientbereichs für einen. Zum Beispiel die <xref:System.Drawing.Graphics.FillRectangle%2A> Methode an den rechten und unteren Rand des angegebenen Rechtecks gefüllt wird, enthalten aber keine dieser Kanten.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Zuordnung von einer Koordinate zu einer anderen  
 In einigen Fällen müssen Sie möglicherweise das Zuordnen von Bildschirmkoordinaten in Clientkoordinaten. Ganz einfach erreichen Sie dies mithilfe der <xref:System.Windows.Forms.Control.PointToClient%2A> und <xref:System.Windows.Forms.Control.PointToScreen%2A> in verfügbaren Methoden der <xref:System.Windows.Forms.Control> Klasse. Z. B. die <xref:System.Windows.Forms.Control.MousePosition%2A> Eigenschaft <xref:System.Windows.Forms.Control> wird gemeldet, in Bildschirmkoordinaten, aber Sie können diese in Clientkoordinaten konvertieren.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
