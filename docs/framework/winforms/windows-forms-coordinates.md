---
title: Windows Forms-Koordinaten
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: ba6bf8c1a8ae5ab14a9b33ae431e34310046b2a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-coordinates"></a>Windows Forms-Koordinaten
Das Koordinatensystem für ein Windows Form basiert auf dem Gerätekoordinaten und die grundlegende Maßeinheit beim Zeichnen in Windows Forms ist die Einheit (in der Regel das Pixel) des Geräts. Punkte auf dem Bildschirm werden vom x- und y-Koordinate-Paaren mit den X-Koordinaten, erhöhen das Recht und die y-Koordinaten erhöhen von oben nach unten beschrieben. Die Position des Ursprungs, relativ zu dem Bildschirm "" variiert abhängig davon, ob Sie Bildschirm- oder Clientkoordinaten angeben.  
  
## <a name="screen-coordinates"></a>Bildschirmkoordinaten  
 Eine Windows Forms-Anwendung gibt die Position eines Fensters auf dem Bildschirm in Bildschirmkoordinaten. Für Bildschirmkoordinaten ist der Ursprung die linke obere Ecke des Bildschirms. Die vollständige Position eines Fensters wird häufig durch beschrieben eine <xref:System.Drawing.Rectangle> Struktur, die die Bildschirmkoordinaten von zwei Punkten, die die linken, oberen und unteren rechten Ecke des Fensters definieren enthält.  
  
## <a name="client-coordinates"></a>Clientkoordinaten  
 Eine Windows Forms-Anwendung gibt die Position der Punkte in einem Formular oder Steuerelement mit dem Clientkoordinaten. Der Ursprung für Clientkoordinaten ist der oberen linken Ecke des Clientbereichs des Steuerelements oder Formulars. Clientkoordinaten stellen Sie sicher, dass eine Anwendung konsistent Koordinatenwerte beim Zeichnen in einem Formular oder Steuerelement, unabhängig von der Position des Formulars oder Steuerelements auf dem Bildschirm verwenden kann.  
  
 Darüber hinaus werden die Abmessungen des Clientbereichs beschrieben durch einen <xref:System.Drawing.Rectangle> Struktur, die Clientkoordinaten für den Bereich enthält. In allen Fällen ist die linke obere Koordinate des Rechtecks in den Clientbereich enthalten, während die untere rechte Koordinate ausgeschlossen ist. Grafikoperationen enthalten nicht den rechten und unteren Rand eines Client-Bereichs. Zum Beispiel die <xref:System.Drawing.Graphics.FillRectangle%2A> Methode an den rechten und unteren Rand des angegebenen Rechtecks voll, aber diese Kanten werden nicht eingeschlossen.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Zuordnung von einem Typ von Koordinate in eine andere  
 In einigen Fällen müssen Sie möglicherweise von Bildschirmkoordinaten in Clientkoordinaten zuordnen. Sie können problemlos zu diesem Zweck verwenden der <xref:System.Windows.Forms.Control.PointToClient%2A> und <xref:System.Windows.Forms.Control.PointToScreen%2A> in verfügbaren Methoden der <xref:System.Windows.Forms.Control> Klasse. Z. B. die <xref:System.Windows.Forms.Control.MousePosition%2A> Eigenschaft <xref:System.Windows.Forms.Control> wird gemeldet, in Bildschirmkoordinaten, aber möglicherweise möchten Sie diese kostenlos in Clientkoordinaten konvertieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
