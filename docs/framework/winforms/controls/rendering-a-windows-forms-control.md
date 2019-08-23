---
title: Wiedergeben eines Windows Forms-Steuerelements
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: b24fbefac0dcfb666e25ad1d1726ef2cf8a5d84e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968274"
---
# <a name="rendering-a-windows-forms-control"></a>Wiedergeben eines Windows Forms-Steuerelements
Rendering bezieht sich auf den Prozess der Erstellung einer visuellen Darstellung auf dem Bildschirm eines Benutzers. Windows Forms verwendet GDI (die neue Windows-Grafikbibliothek) zum Rendern. Die verwalteten Klassen, die Zugriff auf GDI bereitstellen, <xref:System.Drawing?displayProperty=nameWithType> befinden sich im-Namespace und den zugehörigen Subnamespaces.  
  
 Die folgenden Elemente sind am Steuerelement Rendering beteiligt:  
  
- Die von der Basisklasse <xref:System.Windows.Forms.Control?displayProperty=nameWithType>bereitgestellte Zeichnungs Funktionalität.  
  
- Die wesentlichen Elemente der GDI-Grafikbibliothek.  
  
- Die Geometrie des Zeichnungs Bereichs.  
  
- Die Vorgehensweise zum Freigeben von Grafik Ressourcen.  
  
## <a name="drawing-functionality-provided-by-control"></a>Von Steuerelement bereitgestellte Zeichnungsfunktionen  
 Die-Basis <xref:System.Windows.Forms.Control> Klasse stellt Zeichnungsfunktionen <xref:System.Windows.Forms.Control.Paint> über das-Ereignis bereit. Ein-Steuerelement <xref:System.Windows.Forms.Control.Paint> löst das-Ereignis aus, wenn es seine Anzeige aktualisieren muss. Weitere Informationen zu Ereignissen in der .NET Framework finden Sie unter [behandeln und Auswerfen von Ereignissen](../../../standard/events/index.md).  
  
 Die Ereignisdaten Klasse für das <xref:System.Windows.Forms.Control.Paint> Ereignis, <xref:System.Windows.Forms.PaintEventArgs>, enthält die Daten, die zum Zeichnen eines Steuer Elements erforderlich sind – ein Handle für ein Grafik Objekt und ein Rechteck Objekt, das den Bereich darstellt, in dem gezeichnet werden soll. Diese Objekte werden im folgenden Code Fragment in Fett Schrift angezeigt.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics>ist eine verwaltete Klasse, die Zeichnungsfunktionen kapselt, wie in der Erörterung von GDI weiter unten in diesem Thema beschrieben. Bei handelt es sich um eine <xref:System.Drawing.Rectangle> Instanz der-Struktur, die den verfügbaren Bereich definiert, in dem ein Steuerelement gezeichnet werden kann. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Ein Steuerelement Entwickler kann das <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> mithilfe der <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> -Eigenschaft eines-Steuer Elements berechnen, wie in der Erläuterung der Geometrie weiter unten in diesem Thema beschrieben.  
  
 Ein Steuerelement muss Renderinglogik bereit <xref:System.Windows.Forms.Control.OnPaint%2A> stellen, indem die Methode über <xref:System.Windows.Forms.Control>schrieben wird, von der geerbt wird. <xref:System.Windows.Forms.Control.OnPaint%2A>Ruft den Zugriff auf ein Grafik Objekt und ein Rechteck ab, das durch <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> die- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft und die <xref:System.Windows.Forms.PaintEventArgs> -Eigenschaft der-Instanz gezeichnet werden soll.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der- <xref:System.Windows.Forms.Control> Basisklasse implementiert keine Zeichnungsfunktionen <xref:System.Windows.Forms.Control.Paint> , sondern ruft lediglich die Ereignis Delegaten auf, die beim-Ereignis registriert sind. Wenn Sie über <xref:System.Windows.Forms.Control.OnPaint%2A>schreiben, sollten Sie in der <xref:System.Windows.Forms.Control.OnPaint%2A> Regel die-Methode der Basisklasse aufrufen, damit registrierte <xref:System.Windows.Forms.Control.Paint> Delegaten das Ereignis empfangen. Allerdings sollten Steuerelemente, die ihre gesamte Oberfläche zeichnen <xref:System.Windows.Forms.Control.OnPaint%2A>, nicht die Basisklasse aufrufen, da dadurch Flicker eingeführt wird. Ein Beispiel für das Überschreiben <xref:System.Windows.Forms.Control.OnPaint%2A> des Ereignisses finden Sie [unter Gewusst wie: Erstellt ein Windows Forms Steuerelement, das](how-to-create-a-windows-forms-control-that-shows-progress.md)den Fortschritt anzeigt.  
  
> [!NOTE]
> Rufen <xref:System.Windows.Forms.Control.OnPaint%2A> Sie nicht direkt aus dem Steuerelement auf <xref:System.Windows.Forms.Control.Invalidate%2A>. Rufen Sie <xref:System.Windows.Forms.Control.Invalidate%2A> stattdessen die-Methode <xref:System.Windows.Forms.Control>(geerbt von) oder eine andere Methode auf, die aufruft. Die <xref:System.Windows.Forms.Control.Invalidate%2A> -Methode ruft <xref:System.Windows.Forms.Control.OnPaint%2A>wiederum auf. Die <xref:System.Windows.Forms.Control.Invalidate%2A> -Methode ist überladen, und abhängig von den Argumenten, <xref:System.Windows.Forms.Control.Invalidate%2A> die für `e`bereitgestellt werden, zeichnet ein-Steuerelement entweder einen Teil oder den gesamten Bildschirmbereich neu.  
  
 Die- <xref:System.Windows.Forms.Control> Basisklasse definiert eine andere Methode, die zum Zeichnen von <xref:System.Windows.Forms.Control.OnPaintBackground%2A> – die-Methode nützlich ist.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>zeichnet den Hintergrund (und damit die Form) des Fensters und ist sicher, dass er schnell ist, <xref:System.Windows.Forms.Control.OnPaint%2A> während die Details zeichnet und langsamer sein kann, da einzelne Zeichnungs Anforderungen in einem <xref:System.Windows.Forms.Control.Paint> Ereignis kombiniert werden, das alle Bereiche abdeckt, die neu gezeichnet. Möglicherweise möchten Sie den <xref:System.Windows.Forms.Control.OnPaintBackground%2A> aufrufen, wenn Sie beispielsweise einen Hintergrund Hintergrund für das Steuerelement zeichnen möchten.  
  
 Obwohl <xref:System.Windows.Forms.Control.OnPaintBackground%2A> eine Ereignis ähnliche Nomenklatur aufweist und dasselbe Argument wie die `OnPaint` -Methode annimmt, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ist keine echte Ereignismethode. Es ist kein `PaintBackground` Ereignis vorhanden <xref:System.Windows.Forms.Control.OnPaintBackground%2A> , und es werden keine Ereignis Delegaten aufgerufen. Wenn die <xref:System.Windows.Forms.Control.OnPaintBackground%2A> -Methode überschrieben wird, ist es nicht erforderlich, dass <xref:System.Windows.Forms.Control.OnPaintBackground%2A> eine abgeleitete Klasse die-Methode der Basisklasse aufruft.  
  
## <a name="gdi-basics"></a>GDI+-Grundlagen  
 Die <xref:System.Drawing.Graphics> -Klasse stellt Methoden zum Zeichnen verschiedener Formen (z. b. Kreise, Dreiecke, Arcs und Ellipsen) sowie Methoden zum Anzeigen von Text bereit. Der <xref:System.Drawing?displayProperty=nameWithType> -Namespace und seine Subnamespaces enthalten Klassen, die Grafikelemente wie Formen (Kreise, Rechtecke, Arcs usw.), Farben, Schriftarten, Pinsel usw. Kapseln. Weitere Informationen zu GDI finden Sie unter [Verwenden von verwalteten Grafik Klassen](../advanced/using-managed-graphics-classes.md). Die Grundlagen von GDI sind auch [unter Gewusst wie: Erstellt ein Windows Forms Steuerelement, das](how-to-create-a-windows-forms-control-that-shows-progress.md)den Fortschritt anzeigt.  
  
## <a name="geometry-of-the-drawing-region"></a>Geometrie des Zeichnungs Bereichs  
 Die <xref:System.Windows.Forms.Control.ClientRectangle%2A> -Eigenschaft eines Steuer Elements gibt den rechteckigen Bereich an, der für das Steuerelement auf dem Bild <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Schirm des <xref:System.Windows.Forms.PaintEventArgs> Benutzers verfügbar ist, während die-Eigenschaft von den Bereich angibt, der tatsächlich gezeichnet wird. (Beachten Sie, dass das Zeichnen in <xref:System.Windows.Forms.Control.Paint> der Ereignismethode erfolgt, <xref:System.Windows.Forms.PaintEventArgs> die eine-Instanz als Argument annimmt). Ein Steuerelement muss möglicherweise nur einen Teil des verfügbaren Bereichs zeichnen, wie es auch der Fall ist, wenn sich ein kleiner Abschnitt der Anzeige des Steuer Elements ändert. In diesen Fällen muss ein Steuerelement Entwickler das eigentliche Rechteck berechnen, um es zu zeichnen und dieses an <xref:System.Windows.Forms.Control.Invalidate%2A>zu übergeben. Die überladenen <xref:System.Windows.Forms.Control.Invalidate%2A> Versionen von, <xref:System.Drawing.Rectangle> die <xref:System.Drawing.Region> einen oder als Argument akzeptieren, verwenden dieses Argument <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> , um <xref:System.Windows.Forms.PaintEventArgs>die-Eigenschaft von zu generieren.  
  
 Das folgende Code Fragment zeigt, wie `FlashTrackBar` das benutzerdefinierte Steuerelement den rechteckigen Bereich berechnet, in dem gezeichnet werden soll. Die `client` -Variable bezeichnet die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> -Eigenschaft. Ein umfassendes Beispiel finden [Sie unter Gewusst wie: Erstellt ein Windows Forms Steuerelement, das](how-to-create-a-windows-forms-control-that-shows-progress.md)den Fortschritt anzeigt.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Freigeben von Grafik Ressourcen  
 Grafik Objekte sind aufwendig, da Sie Systemressourcen verwenden. Zu diesen Objekten zählen Instanzen der <xref:System.Drawing.Graphics?displayProperty=nameWithType> -Klasse sowie Instanzen von <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>und anderen Grafik Klassen. Es ist wichtig, dass Sie nur dann eine Grafik Ressource erstellen, wenn Sie Sie benötigen, und Sie nach der Verwendung sofort freigeben. Wenn Sie einen Typ erstellen, der die <xref:System.IDisposable> -Schnittstelle implementiert <xref:System.IDisposable.Dispose%2A> , rufen Sie die zugehörige-Methode auf, wenn Sie damit fertig sind, um Ressourcen freizugeben.  
  
 Das folgende Code Fragment zeigt, wie `FlashTrackBar` das benutzerdefinierte Steuerelement eine <xref:System.Drawing.Brush> Ressource erstellt und freigibt. Den gesamten Quellcode finden [Sie unter Gewusst wie: Erstellt ein Windows Forms Steuerelement, das](how-to-create-a-windows-forms-control-that-shows-progress.md)den Fortschritt anzeigt.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das den Fortschritt anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md)
