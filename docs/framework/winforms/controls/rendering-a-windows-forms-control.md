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
ms.openlocfilehash: 9641b6906bc2acaa525aed6df57f189d39317d35
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614674"
---
# <a name="rendering-a-windows-forms-control"></a>Wiedergeben eines Windows Forms-Steuerelements
Rendering bezieht sich auf den Prozess der Erstellung einer visuellen Darstellung auf dem Bildschirm des Benutzers. Windows Forms verwendet [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (die neue Windows-Grafikbibliothek) für das Rendering. Die verwalteten Klassen, die Zugriff auf ermöglichen [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] befinden sich in der <xref:System.Drawing?displayProperty=nameWithType> Namespace und dessen untergeordneten Namespaces.  
  
 Die folgenden Elemente sind beim Rendern von Steuerelementen beteiligt:  
  
- Zeichnen von der Basisklasse bereitgestellte Funktionalität <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
- Die Hauptkomponenten der [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Grafikbibliothek.  
  
- Die Geometrie den Zeichnungsbereich.  
  
- Die Prozedur für das Freigeben von Grafikressourcen.  
  
## <a name="drawing-functionality-provided-by-control"></a>Zeichnen die Funktionalität, die vom Steuerelement  
 Die Basisklasse <xref:System.Windows.Forms.Control> über Zeichnungsfunktionalität bietet die <xref:System.Windows.Forms.Control.Paint> Ereignis. Ein Steuerelement löst die <xref:System.Windows.Forms.Control.Paint> Ereignis immer, wenn er benötigt, um dessen Anzeige zu aktualisieren. Weitere Informationen zu Ereignissen in .NET Framework finden Sie unter [behandeln und Auslösen von Ereignissen](../../../standard/events/index.md).  
  
 Die Ereignisdatenklasse für die <xref:System.Windows.Forms.Control.Paint> Ereignis <xref:System.Windows.Forms.PaintEventArgs>, die für das Zeichnen eines Steuerelements benötigten Daten enthält, ein Handle für ein Graphics-Objekt und ein Rechteckobjekt, das den Bereich für das Zeichnen darstellt. Diese Objekte werden in angezeigt. im folgenden Codefragment fett gedruckt erscheint.  
  
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
  
 <xref:System.Drawing.Graphics> ist eine verwaltete Klasse, die Zeichnen-Funktionalität kapselt, wie beschrieben in der Diskussion [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] weiter unten in diesem Thema. Der <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ist eine Instanz der <xref:System.Drawing.Rectangle> Struktur und definiert den verfügbaren Bereich, in dem ein Steuerelement zeichnen kann. Der Entwickler eines Steuerelements kann berechnen, die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> mithilfe der <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft eines Steuerelements, wie bei der Erläuterung der Geometry-Instanz weiter unten in diesem Thema beschrieben.  
  
 Ein Steuerelement muss Renderinglogik bereitstellen, durch Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode, die es erbt <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A> erhält Zugriff auf ein Graphics-Objekt und ein Rechteck für über das Zeichnen der <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> und <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaften der <xref:System.Windows.Forms.PaintEventArgs> -Instanz übergeben wird.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse <xref:System.Windows.Forms.Control> Klasse implementiert keine Zeichnungsfunktionen nicht, aber ruft lediglich den Ereignisdelegaten, der registriert werden die <xref:System.Windows.Forms.Control.Paint> Ereignis. Beim Überschreiben <xref:System.Windows.Forms.Control.OnPaint%2A>, Sie sollten in der Regel rufen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode der Basisklasse, damit Delegaten registrierte empfangen die <xref:System.Windows.Forms.Control.Paint> Ereignis. Jedoch sollten Steuerelemente, die ihre gesamte Oberfläche Zeichnen nicht der Basisklasse aufrufen <xref:System.Windows.Forms.Control.OnPaint%2A>, Flimmern. Ein Beispiel für das Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Ereignis finden Sie unter der [Vorgehensweise: Erstellen ein Windows Forms-Steuerelements, die Status anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  Nicht aufgerufen werden <xref:System.Windows.Forms.Control.OnPaint%2A> direkt über Ihr Steuerelement; stattdessen Aufrufen der <xref:System.Windows.Forms.Control.Invalidate%2A> -Methode (geerbt von <xref:System.Windows.Forms.Control>) oder eine andere Methode, die aufruft <xref:System.Windows.Forms.Control.Invalidate%2A>. Die <xref:System.Windows.Forms.Control.Invalidate%2A> Methode wiederum ruft <xref:System.Windows.Forms.Control.OnPaint%2A>. Die <xref:System.Windows.Forms.Control.Invalidate%2A> Methode überladen ist, und, abhängig von den Argumenten für angegebene <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, ein Steuerelement neu gezeichnet wird, einige oder alle der Bildschirmbereich.  
  
 Die Basis <xref:System.Windows.Forms.Control> -Klasse definiert eine andere Methode, die zum Zeichnen hilfreich sind, die <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Methode.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Zeichnet den Hintergrund (und somit auch der Form ") des Fensters wird garantiert, schnell, während <xref:System.Windows.Forms.Control.OnPaint%2A> zeichnet die Details und möglicherweise daran, dass einzelne zeichnungsanforderungen zusammengefasst werden langsamer <xref:System.Windows.Forms.Control.Paint> -Ereignis, das alle Bereiche abdeckt, die sein neu gezeichnet. Möglicherweise möchten Sie rufen die <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Wenn, z. B. einen Hintergrund mit Farbverlauf für das Steuerelement gezeichnet werden sollen.  
  
 Während <xref:System.Windows.Forms.Control.OnPaintBackground%2A> verfügt über ein ereignisähnliches Terminologie und nimmt des gleichen Arguments wie die `OnPaint` Methode <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ist keine Ereignismethode "true"-. Es gibt keine `PaintBackground` Ereignis und <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Ereignisdelegaten nicht aufgerufen. Beim Überschreiben der <xref:System.Windows.Forms.Control.OnPaintBackground%2A> -Methode eine abgeleitete Klasse ist nicht erforderlich, zum Aufrufen der <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Methode ihrer Basisklasse.  
  
## <a name="gdi-basics"></a>Grundlagen von GDI +  
 Die <xref:System.Drawing.Graphics> Klasse enthält Methoden zum Zeichnen verschiedener Formen wie z. B. Kreise, Dreiecke, Ellipsen und Bögen sowie Methoden zum Anzeigen von Text. Die <xref:System.Drawing?displayProperty=nameWithType> und dessen untergeordnete Namespaces enthalten Klassen, die Grafikelemente wie z. B. Formen (Kreise, Rechtecke, Bögen und andere), Farben, Schriftarten, Pinseln und So weiter zu kapseln. Weitere Informationen zu [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], finden Sie unter [mithilfe von verwalteten Grafikklassen](../advanced/using-managed-graphics-classes.md). Die Grundlagen der [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Außerdem wird beschrieben, der [Vorgehensweise: Erstellen ein Windows Forms-Steuerelements, die Status anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Die Geometrie des Zeichenbereichs  
 Die <xref:System.Windows.Forms.Control.ClientRectangle%2A> Eigenschaft eines Steuerelements gibt an, der rechteckige Bereich, der für das Steuerelement auf dem Bildschirm des Benutzers, während die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft <xref:System.Windows.Forms.PaintEventArgs> gibt an, der Bereich, der tatsächlich gezeichnet wird. (Denken Sie daran, dass zeichnen, in durchgeführt wird der <xref:System.Windows.Forms.Control.Paint> Ereignismethode, die akzeptiert eine <xref:System.Windows.Forms.PaintEventArgs> Instanz als Argument). Ein Steuerelement müssen möglicherweise nur einen Teil der verfügbare Bereich, gezeichnet werden soll, wie die Groß-/Kleinschreibung bei der ein kleiner Abschnitt der Steuerelements geändert wird. In diesen Fällen erhalten Entwickler eines Steuerelements muss das aktuelle Rechteck aus, um das Zeichnen und übergibt diese an berechnen <xref:System.Windows.Forms.Control.Invalidate%2A>. Die überladenen Version von <xref:System.Windows.Forms.Control.Invalidate%2A> , nehmen eine <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.Region> als Argument verwenden, generieren die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft <xref:System.Windows.Forms.PaintEventArgs>.  
  
 Das folgende Codefragment zeigt die `FlashTrackBar` benutzerdefiniertes Steuerelement berechnet den rechteckigen Bereich für das Zeichnen. Die `client` Variable kennzeichnet den <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft. Ein vollständiges Beispiel finden Sie unter [Vorgehensweise: Erstellen ein Windows Forms-Steuerelements, die Status anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Freigeben von Grafikressourcen  
 Grafikobjekte sind aufwändig, da sie Systemressourcen verwenden. Solche Objekte sind Instanzen der <xref:System.Drawing.Graphics?displayProperty=nameWithType> sowie Instanzen der Klasse <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, und andere Grafikklassen. Es ist wichtig, dass Sie eine Grafik-Ressource erstellen, nur, wenn Sie benötigen, und freigegeben werden, sobald Sie nicht mehr verwenden werden. Wenn Sie einen Typ erstellen, die implementiert die <xref:System.IDisposable> Schnittstelle, rufen Sie die <xref:System.IDisposable.Dispose%2A> Methode, wenn Sie damit fertig sind, um Ressourcen freizugeben.  
  
 Das folgende Codefragment zeigt wie die `FlashTrackBar` benutzerdefiniertes Steuerelement erstellt und wieder eine <xref:System.Drawing.Brush> Ressource. Den vollständigen Quellcode, finden Sie unter [Vorgehensweise: Erstellen ein Windows Forms-Steuerelements, die Status anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen Sie ein Windows Forms-Steuerelement, das ausgeführt wird.](how-to-create-a-windows-forms-control-that-shows-progress.md)
