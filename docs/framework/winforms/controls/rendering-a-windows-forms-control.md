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
ms.openlocfilehash: a2d7a02e725e3f8065b80a6b30ea21158be43ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="rendering-a-windows-forms-control"></a>Wiedergeben eines Windows Forms-Steuerelements
Rendering bezieht sich auf den Prozess zum Erstellen einer visuellen Darstellung auf dem Bildschirm des Benutzers. Windows Forms verwendet [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (die neue Windows-Grafikbibliothek) für das Rendering. Die verwalteten Klassen, die Zugriff auf [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] befinden sich in der <xref:System.Drawing?displayProperty=nameWithType> Namespace und dessen untergeordneten Namespaces.  
  
 Die folgenden Elemente werden beim Rendern von Steuerelementen beteiligt:  
  
-   Zeichnen von der Basisklasse bereitgestellten Funktionen <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
-   Die wichtigsten Elemente der der [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Grafikbibliothek.  
  
-   Die Geometrie den Zeichnungsbereich.  
  
-   Die Prozedur für die Freigabe Grafikressourcen.  
  
## <a name="drawing-functionality-provided-by-control"></a>Zeichnen von Steuerelement bereitgestellte Funktionalität  
 Die Basisklasse <xref:System.Windows.Forms.Control> bietet zeichnen-Funktionalität über seine <xref:System.Windows.Forms.Control.Paint> Ereignis. Löst ein Steuerelement die <xref:System.Windows.Forms.Control.Paint> Ereignis aus, wenn seine Anzeige aktualisiert werden muss. Weitere Informationen zu Ereignissen in .NET Framework finden Sie unter [behandeln und Auslösen von Ereignissen](../../../../docs/standard/events/index.md).  
  
 Die Ereignisdatenklasse für das <xref:System.Windows.Forms.Control.Paint> Ereignis <xref:System.Windows.Forms.PaintEventArgs>, enthält die Daten für das Zeichnen eines Steuerelements benötigt – ein Handle für ein Grafikobjekt und ein Rechteckobjekt, das den Bereich für das Zeichnen darstellt. Diese Objekte in angezeigt werden, in das folgende Codefragment fett formatiert.  
  
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
  
 <xref:System.Drawing.Graphics> ist eine verwaltete Klasse, die Zeichnen Funktionen kapselt, gemäß der bei der Erläuterung der [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] weiter unten in diesem Thema. Die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ist eine Instanz der <xref:System.Drawing.Rectangle> strukturieren und definiert den verfügbaren Bereich, in dem ein Steuerelement zeichnen kann. Der Entwickler eines Steuerelements kann Berechnen der <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> mithilfe der <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft eines Steuerelements, wie bei der Erläuterung der Geometrie weiter unten in diesem Thema beschrieben.  
  
 Ein Steuerelement muss Renderinglogik bereitstellen, durch Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode, die von der erbt <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A> Ruft den Zugriff auf ein Grafikobjekt und ein Rechteck über gezeichnet werden soll, der <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> und die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaften der <xref:System.Windows.Forms.PaintEventArgs> -Instanz übergeben wird.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse <xref:System.Windows.Forms.Control> Klasse keine Funktion implementiert, sondern ruft lediglich die Ereignisdelegaten, der registriert werden die <xref:System.Windows.Forms.Control.Paint> Ereignis. Beim Überschreiben <xref:System.Windows.Forms.Control.OnPaint%2A>, rufen Sie in der Regel die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse, damit Delegaten registrierte empfangen die <xref:System.Windows.Forms.Control.Paint> Ereignis. Jedoch sollten Steuerelemente, die ihre gesamte Oberfläche Zeichnen nicht der Basisklasse aufrufen <xref:System.Windows.Forms.Control.OnPaint%2A>, Flimmern. Für ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> -Ereignis finden Sie unter der [wie: Erstellen einer Windows Forms-Steuerelement, dass zeigt Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  Nicht aufgerufen werden <xref:System.Windows.Forms.Control.OnPaint%2A> direkt über das Steuerelement, rufen Sie stattdessen die <xref:System.Windows.Forms.Control.Invalidate%2A> -Methode (geerbt von <xref:System.Windows.Forms.Control>) oder eine andere Methode, die aufruft <xref:System.Windows.Forms.Control.Invalidate%2A>. Die <xref:System.Windows.Forms.Control.Invalidate%2A> Methode wiederum ruft <xref:System.Windows.Forms.Control.OnPaint%2A>. Die <xref:System.Windows.Forms.Control.Invalidate%2A> -Methode ist überladen, und abhängig von den Argumenten für angegebene <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, ein Steuerelement neu gezeichnet wird, einige oder alle seine Bildschirmbereichs.  
  
 Die Basis <xref:System.Windows.Forms.Control> Klasse definiert eine andere Methode, die zum Zeichnen hilfreich sind – die <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Methode.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Zeichnet den Hintergrund (und somit der Form ") des Fensters und ist garantiert schnelles <xref:System.Windows.Forms.Control.OnPaint%2A> zeichnet die Details und möglicherweise daran, dass einzelne zeichnungsanforderungen zusammengefasst werden langsamer <xref:System.Windows.Forms.Control.Paint> Ereignis, das alle Bereiche behandelt, die sein neu gezeichnet wird. Möglicherweise möchten Sie rufen die <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Wenn z. B. einen Farbverlauf-Hintergrund für das Steuerelement gezeichnet werden soll.  
  
 Während <xref:System.Windows.Forms.Control.OnPaintBackground%2A> hat eine ereignisähnliches Nomenklatur und des gleichen Arguments wie die `OnPaint` Methode <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ist keine Ereignismethode "true"-. Es ist keine `PaintBackground` Ereignis und <xref:System.Windows.Forms.Control.OnPaintBackground%2A> keine Ereignisdelegaten aufgerufen werden. Zum Überschreiben der <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Methode, eine abgeleitete Klasse ist nicht erforderlich, um das Aufrufen der <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Methode ihrer Basisklasse.  
  
## <a name="gdi-basics"></a>Grundlagen von GDI +  
 Die <xref:System.Drawing.Graphics> -Klasse stellt Methoden für das Zeichnen von verschiedenen Formen wie Kreise, Dreiecke Bögen und Ellipsen, sowie Methoden zum Anzeigen von Text. Die <xref:System.Drawing?displayProperty=nameWithType> und dessen untergeordnete Namespaces enthalten Klassen, die Grafikelemente z. B. Formen (Kreise, Rechtecke, Bögen usw.), Farben, Schriftarten, Pinsel und So weiter zu kapseln. Weitere Informationen zu [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], finden Sie unter [mithilfe von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md). Die Grundlagen der [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] werden auch in beschrieben die [Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass zeigt Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Die Geometrie des Zeichenbereichs  
 Die <xref:System.Windows.Forms.Control.ClientRectangle%2A> Eigenschaft eines Steuerelements gibt rechteckigen Bereich zur Verfügung, um das Steuerelement auf dem Bildschirm des Benutzers, während die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft <xref:System.Windows.Forms.PaintEventArgs> gibt den Bereich, der tatsächlich gezeichnet wird. (Beachten Sie, dass Zeichnen in erfolgt der <xref:System.Windows.Forms.Control.Paint> Ereignismethode, die akzeptiert eine <xref:System.Windows.Forms.PaintEventArgs> Instanz als Argument). Ein Steuerelement müssen nur einen Teil der verfügbare Bereich zu zeichnen, wie ist der Fall, wenn ein kleiner Abschnitt der Änderungen für das Steuerelement angezeigt wird. In solchen Situationen muss ein Entwickler von Steuerelementen der tatsächlichen Rechteck zum Zeichnen und übergeben, um berechnen <xref:System.Windows.Forms.Control.Invalidate%2A>. Der überladenen Versionen der <xref:System.Windows.Forms.Control.Invalidate%2A> nehmen eine <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.Region> als Argument verwenden, generieren die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft <xref:System.Windows.Forms.PaintEventArgs>.  
  
 Das folgende Codefragment zeigt wie die `FlashTrackBar` benutzerdefiniertes Steuerelement berechnet den rechteckigen Bereich zu zeichnen. Die `client` Variable kennzeichnet den <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Eigenschaft. Ein vollständiges Beispiel finden Sie unter [Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass zeigt Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Dies spart Grafikressourcen  
 Grafikobjekten sind teuer, da sie Systemressourcen verwenden. Solche Objekte sind Instanzen der <xref:System.Drawing.Graphics?displayProperty=nameWithType> sowie Instanzen der Klasse <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, und andere Grafikklassen. Es ist wichtig, dass Sie eine Ressource Grafiken erstellen, nur, wenn Sie ihn benötigen, und freigegeben werden, sobald Sie mit der sie fertig sind. Wenn Sie einen Typ erstellen, die implementiert die <xref:System.IDisposable> Schnittstelle, rufen Sie die <xref:System.IDisposable.Dispose%2A> Methode, wenn Sie damit fertig sind, um Ressourcen freizugeben.  
  
 Das folgende Codefragment zeigt wie die `FlashTrackBar` benutzerdefiniertes Steuerelement erstellt, und gibt eine <xref:System.Drawing.Brush> Ressource. Den vollständigen Quellcode, finden Sie unter [Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass zeigt Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen eines Windows Forms-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
