---
title: "Wiedergeben eines Windows&#160;Forms-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Grafikressourcen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Ungültigkeit und Zeichnen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Rendern"
  - "OnPaintBackground-Methode, Aufrufen in benutzerdefinierten Windows Forms-Steuerelementen"
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Wiedergeben eines Windows&#160;Forms-Steuerelements
Als Rendering wird ein Prozess bezeichnet, durch den eine visuelle Repräsentation auf dem Bildschirm eines Benutzers erzeugt wird.  Windows Forms verwendet zum Rendern [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] \(die neue Windows\-Graphikbibliothek\).  Die verwalteten Klassen, die den Zugriff auf [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] ermöglichen, befinden sich im <xref:System.Drawing?displayProperty=fullName>\-Namespace und in dessen untergeordneten Namespaces.  
  
 Die folgenden Elemente spielen beim Rendern von Steuerelementen eine Rolle:  
  
-   Die Zeichnungsfunktionalität, die von der <xref:System.Windows.Forms.Control?displayProperty=fullName>\-Basisklasse bereitgestellt wird.  
  
-   Die wichtigsten Elemente der [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\-Graphikbibliothek.  
  
-   Die Geometrie des Bereichs, in dem gezeichnet wird.  
  
-   Das Verfahren, mit dem Graphikressourcen freigegeben werden.  
  
## Vom Steuerelement bereitgestellte Zeichnungsfunktionen  
 Die <xref:System.Windows.Forms.Control>\-Basisklasse stellt über das <xref:System.Windows.Forms.Control.Paint>\-Ereignis Zeichnungsfunktionalität bereit.  Ein Steuerelement löst das <xref:System.Windows.Forms.Control.Paint>\-Ereignis immer dann aus, wenn seine Anzeige aktualisiert werden muss.  Weitere Informationen über Ereignisse in .NET Framework finden Sie unter [Behandeln und Auslösen von Ereignissen](../../../../docs/standard/events/index.md).  
  
 Die Ereignisdatenklasse für das <xref:System.Windows.Forms.Control.Paint>\-Ereignis, <xref:System.Windows.Forms.PaintEventArgs>, beinhaltet die Daten, die für das Zeichnen des Steuerelements benötigt werden – ein Handle eines Graphikobjekts und ein rechteckiges Objekt, das den Bereich darstellt, in dem gezeichnet wird.  Diese Objekte sind im folgenden Codefragment fett dargestellt.  
  
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
  
 <xref:System.Drawing.Graphics> ist eine verwaltete Klasse, die Zeichnungsfunktionen kapselt. Dies wird im Abschnitt zu [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] weiter unten in diesem Thema beschrieben.  <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ist eine Instanz der <xref:System.Drawing.Rectangle>\-Struktur und definiert den verfügbaren Bereich, in dem ein Steuerelement zeichnen kann.  Der Entwickler eines Steuerelements kann <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> mithilfe der <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Eigenschaft eines Steuerelements berechnen. Dies wird weiter unten im Abschnitt zur Geometrie beschrieben.  
  
 Ein Steuerelement muss Renderlogik bereitstellen, indem die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode, die es von <xref:System.Windows.Forms.Control> erbt, überschrieben wird.  <xref:System.Windows.Forms.Control.OnPaint%2A> erhält mithilfe der <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A>\-Eigenschaft und der <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Eigenschaft der übergebenen <xref:System.Windows.Forms.PaintEventArgs>\-Instanz Zugriff auf ein Graphikobjekt und ein Rechteck, in dem gezeichnet werden soll.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode der Basisklasse von <xref:System.Windows.Forms.Control> implementiert keine Zeichnungsfunktionen, sondern ruft lediglich die Ereignisdelegaten auf, die mit dem <xref:System.Windows.Forms.Control.Paint>\-Ereignis registriert sind.  Beim Überschreiben von <xref:System.Windows.Forms.Control.OnPaint%2A> sollten Sie im Normalfall die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode der Basisklasse aufrufen, sodass registrierte Delegaten das <xref:System.Windows.Forms.Control.Paint>\-Ereignis empfangen.  Allerdings sollten Steuerelemente, die ihre gesamte Oberfläche zeichnen, nicht die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode der Basisklasse aufrufen, um Flimmern zu vermeiden.  Ein Beispiel zum Überschreiben des <xref:System.Windows.Forms.Control.OnPaint%2A>\-Ereignisses finden Sie unter [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  Rufen Sie <xref:System.Windows.Forms.Control.OnPaint%2A> nicht direkt über das Steuerelement auf, sondern über die von <xref:System.Windows.Forms.Control> geerbte <xref:System.Windows.Forms.Control.Invalidate%2A>\-Methode oder eine andere Methode, die <xref:System.Windows.Forms.Control.Invalidate%2A> aufruft.  Die <xref:System.Windows.Forms.Control.Invalidate%2A>\-Methode ruft wiederum <xref:System.Windows.Forms.Control.OnPaint%2A> auf.  Die <xref:System.Windows.Forms.Control.Invalidate%2A>\-Methode wird überladen. Ein Steuerelement zeichnet abhängig von den für <xref:System.Windows.Forms.Control.Invalidate%2A> angegebenen Argumenten seinen Bildschirmbereich teilweise oder vollständig neu.  
  
 Durch die Basisklasse von <xref:System.Windows.Forms.Control> wird eine andere Methode definiert, die für das Zeichnen von Nutzen ist: die <xref:System.Windows.Forms.Control.OnPaintBackground%2A>\-Methode.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 Mit <xref:System.Windows.Forms.Control.OnPaintBackground%2A> wird der Hintergrund \(und dadurch auch die Form\) des Fensters gezeichnet und schnelles Vorgehen gewährleistet. Dagegen dient <xref:System.Windows.Forms.Control.OnPaint%2A> dem Zeichnen von Details, wodurch diese Methode langsamer ist, da einzelne Anforderungen zum Zeichnen in einem <xref:System.Windows.Forms.Control.Paint>\-Ereignis zusammengefasst werden, das alle erneut zu zeichnenden Bereiche abdeckt.  Sie können <xref:System.Windows.Forms.Control.OnPaintBackground%2A> z. B. dann aufrufen, wenn Sie für das Steuerelement einen Hintergrund mit Farbverlauf zeichnen möchten.  
  
 Obwohl <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Bezeichnungen verwendet, die der einer Ereignismethode ähnlich sind, und sie dasselbe Argument wie die `OnPaint`\-Methode unterstützt, ist <xref:System.Windows.Forms.Control.OnPaintBackground%2A> dennoch keine Ereignismethode.  Es gibt kein `PaintBackground`\-Ereignis, und von <xref:System.Windows.Forms.Control.OnPaintBackground%2A> werden keine Ereignisdelegaten aufgerufen.  Beim Überschreiben der <xref:System.Windows.Forms.Control.OnPaintBackground%2A>\-Methode ist es nicht notwendig, dass die abgeleitete Klasse die <xref:System.Windows.Forms.Control.OnPaintBackground%2A>\-Methode ihrer Basisklasse aufruft.  
  
## Grundlagen von GDI\+  
 Die <xref:System.Drawing.Graphics>\-Klasse stellt Methoden zum Zeichnen verschiedener Formen, z. B. von Kreisen, Dreiecken, Bögen und Ellipsen, sowie Methoden zum Anzeigen von Text zur Verfügung.  Der <xref:System.Drawing?displayProperty=fullName>\-Namespace und seine untergeordneten Namespaces enthalten Klassen, die grafische Elemente wie Formen \(Kreise, Rechtecke, Bögen u. a.\), Farben, Schriftarten, Pinsel usw. umfassen.  Weitere Informationen zu [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] finden Sie unter [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md).  Die wichtigsten Aspekte von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] werden zudem unter [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md) beschrieben.  
  
## Geometrie des Zeichenbereichs  
 Die <xref:System.Windows.Forms.Control.ClientRectangle%2A>\-Eigenschaft eines Steuerelements legt den rechteckigen Bereich fest, der für das Steuerelement auf dem Bildschirm des Benutzers verfügbar ist, während die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Eigenschaft von <xref:System.Windows.Forms.PaintEventArgs> den Bereich festlegt, der tatsächlich gezeichnet wird.  \(Beachten Sie, dass das Zeichnen durch die <xref:System.Windows.Forms.Control.Paint>\-Ereignismethode erfolgt, die eine <xref:System.Windows.Forms.PaintEventArgs>\-Instanz als Argument verwendet\).  Ein Steuerelement muss seinen verfügbaren Bereich möglicherweise nur teilweise zeichnen, z. B. dann, wenn nur ein kleiner Ausschnitt des angezeigten Steuerelements geändert wird.  In solchen Fällen muss der Entwickler des Steuerelements das tatsächlich zu zeichnende Rechteck berechnen und es an <xref:System.Windows.Forms.Control.Invalidate%2A> weitergeben.  Die überladenen Versionen von <xref:System.Windows.Forms.Control.Invalidate%2A>, die ein <xref:System.Drawing.Rectangle> oder einen <xref:System.Drawing.Region> als Argument verwenden, generieren hiermit die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Eigenschaft von <xref:System.Windows.Forms.PaintEventArgs>.  
  
 Im folgenden Codefragment wird gezeigt, wie das benutzerdefinierte Steuerelement `FlashTrackBar` den rechteckigen Bereich berechnet, in dem gezeichnet werden soll.  Die `client`\-Variable kennzeichnet die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>\-Eigenschaft.  Ein vollständiges Beispiel finden Sie unter [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## Freigeben von Graphikressourcen  
 Die Verwendung graphischer Objekte ist aufwendig, da diese Systemressourcen verwenden.  Zu diesen Objekten gehören Instanzen der <xref:System.Drawing.Graphics?displayProperty=fullName>\-Klasse sowie Instanzen von <xref:System.Drawing.Brush?displayProperty=fullName>, <xref:System.Drawing.Pen?displayProperty=fullName> und anderen Graphikklassen.  Es ist wichtig, dass Sie eine graphische Ressource nur bei Bedarf erstellen und diese wieder freigeben, sobald sie nicht mehr verwendet wird.  Wenn Sie einen Typ erstellen, der die <xref:System.IDisposable>\-Schnittstelle implementiert, rufen Sie seine <xref:System.IDisposable.Dispose%2A>\-Methode auf, sobald er nicht mehr verwendet wird, um Ressourcen freizugeben.  
  
 Im folgendem Codefragment wird gezeigt, wie durch das benutzerdefinierte `FlashTrackBar`\-Steuerelement eine <xref:System.Drawing.Brush>\-Ressource erstellt und wieder freigegeben wird.  Den vollständigen Quellcode finden Sie unter [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## Siehe auch  
 [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)