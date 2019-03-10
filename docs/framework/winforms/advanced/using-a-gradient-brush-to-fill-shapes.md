---
title: Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 5771aaabd283d71f5fa6934f86a1c24a57f38dca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704387"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen
Sie können einen Pinsel mit Farbverlauf verwenden, zum Ausfüllen einer Form mit einem Farbverlauf. Einen horizontalen Farbverlauf können Sie beispielsweise um eine Form mit Farbe zu füllen, die nach und nach ändert, während Sie am rechten Rand aus dem linken Rand der Form bewegen. Stellen Sie sich vor einem Rechteck mit einem linken Rand, der Schwarz ist (dargestellt durch die Rot-, Grün- und Blau-Komponenten, 0, 0, 0) und einer rechten Rand, d. h. Rot (dargestellt durch 255, 0, 0). Wenn das Rechteck 256 Pixel breit ist, werden die Rotanteils der ein angegebenes Pixel eins größer ist als der Rotanteil des Pixels auf der linken Seite. Das ganz linke Pixel in einer Zeile hat Farbkomponenten (0, 0, 0), das zweite Pixel hat (1, 0, 0), das dritte Pixel (2, 0, 0), und So weiter, bis Sie auf der äußersten rechten Pixel, die Farbkomponenten (255, 0, 0) verfügt. Diese interpolierten Farbwerte bilden zusammen den Farbverlauf.  
  
 Ein linearer Farbverlauf wird die Farbe ändert, horizontal, vertikal oder parallel zu einer diagonalen Linie. Ein linearen Pfadfarbverlaufs ändert Farbe, wenn Sie über die innere und eine Grenze eines Pfads verschieben. Sie können anpassen, dass Pfadfarbverläufe, um eine Vielzahl von Effekte zu erzielen.  
  
 Die folgende Abbildung zeigt ein Rechteck, die mit einem linearen Farbverlaufspinsel gefüllt, und eine Ellipse mit einem Pfad Farbverlaufspinsel gefüllt.  
  
 ![Farbverlauf](./media/gradient2.png "gradient2")  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen eines linearen Farbverlaufs](how-to-create-a-linear-gradient.md)  
 Zeigt, wie zum Erstellen eines linearen Farbverlauf mithilfe der <xref:System.Drawing.Drawing2D.LinearGradientBrush> Klasse.  
  
 [Vorgehensweise: Erstellen eines linearen Pfadfarbverlaufs](how-to-create-a-path-gradient.md)  
 Beschreibt, wie Sie einen Pfad Farbverlauf mithilfe der <xref:System.Drawing.Drawing2D.PathGradientBrush> Klasse.  
  
 [Vorgehensweise: Anwenden der Gammakorrektur bei einem Farbverlauf](how-to-apply-gamma-correction-to-a-gradient.md)  
 Erläutert, wie Sie Gammakorrektur mit einem Farbverlaufspinsel verwenden.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.
