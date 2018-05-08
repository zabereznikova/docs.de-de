---
title: Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 857a9276a731ae5e69b3caa1a639d1315aba9901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen
Sie können einen Pinsel mit Farbverlauf verwenden, zum Ausfüllen einer Form mit einem Farbverlauf. Beispielsweise können Sie einen horizontalen Farbverlauf, eine Form Farbe gefüllt, die allmählich ändert, wie Sie vom linken Rand der Form an den rechten Rand verschieben. Stellen Sie sich vor einem Rechteck, mit einer linken Kante, die Schwarz ist (dargestellt durch Rot-, Grün- und Blau-Komponenten, 0, 0, 0) und einer rechten Rand, d. h. Rot (dargestellt durch 255, 0, 0). Wenn das Rechteck 256 Pixel breit ist, wird die rote Komponente eines bestimmten Pixels eins größer als die rote Komponente des Pixels auf der linken Seite. Das ganz linke Pixel in einer Zeile hat Farbkomponenten (0, 0, 0), das zweite Pixel hat (1, 0, 0), das dritte Pixel (2, 0, 0), und So weiter, bis zum äußersten rechten Pixel gelangen Farbkomponenten (255, 0, 0) besitzt. Diese interpolierten Farbwerte machen den Farbverlauf aus.  
  
 Ein linearer Farbverlauf ändert Farbe, wie horizontal und/oder vertikal zu verschieben oder parallel zu einer angegebenen schräge Linie. Ein linearen Pfadfarbverlaufs ändert Farbe, während Sie über die innere und die Grenze eines Pfads bewegen. Pfadfarbverläufe um eine Vielzahl von Effekte erzielen kann angepasst werden.  
  
 Die folgende Abbildung zeigt ein Rechteck mit einem linearen Farbverlaufspinsel und eine Ellipse gefüllt mit einem Pinsel mit Farbverlauf.  
  
 ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Erstellen eines linearen Farbverlaufs](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 Zeigt, wie ein linearer Farbverlauf mithilfe der <xref:System.Drawing.Drawing2D.LinearGradientBrush> Klasse.  
  
 [Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 Enthält Informationen zum Erstellen eines Farbverlaufs mithilfe der <xref:System.Drawing.Drawing2D.PathGradientBrush> Klasse.  
  
 [Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 Erläutert die Gammakorrektur mit einem Farbverlaufspinsel verwendet.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.
