---
title: "Pfadmarkupsyntax | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PathGeometry-Klasse"
  - "Attributverwendung in XAML"
  - "XAML-Attributen"
  - "PathGeometry-Klassen"
  - "Grafiken, PathGeometry-Klasse"
  - "XAML-Objektelementen"
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Pfadmarkupsyntax
Pfade finden Sie im Abschnitt [Shapes and Basic Drawing in WPF Overview](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) und [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md), jedoch in diesem Thema im Detail leistungsfähigere und komplexere Mini wird die Sprache beschrieben Pfadgeometrien stärker mit angeben können [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 Dieses Thema enthält folgende Abschnitte:  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie mit den grundlegenden Funktionen von vertraut sein <xref:System.Windows.Media.Geometry> Objekte. Weitere Informationen finden Sie unter der [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry und PathFigureCollection Mini-Sprachen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt zwei Klassen, die Mini-Sprachen zum Beschreiben von geometrische Pfade bereitstellen: <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.PathFigureCollection>.  
  
-   Verwenden Sie die <xref:System.Windows.Media.StreamGeometry> Mini Sprache beim Festlegen einer Eigenschaft vom Typ <xref:System.Windows.Media.Geometry>, wie z. B. die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft ein <xref:System.Windows.UIElement> oder <xref:System.Windows.Shapes.Path.Data%2A> -Eigenschaft des eine <xref:System.Windows.Shapes.Path> Element. Im folgenden Beispiel wird die Attributsyntax zum Erstellen einer <xref:System.Windows.Media.StreamGeometry>.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   Verwenden Sie die <xref:System.Windows.Media.PathFigureCollection> Mini Sprache beim Festlegen der <xref:System.Windows.Media.PathGeometry.Figures%2A> Eigenschaft ein <xref:System.Windows.Media.PathGeometry>. Im folgenden Beispiel wird eine Attributsyntax zum Erstellen einer <xref:System.Windows.Media.PathFigureCollection> für eine <xref:System.Windows.Media.PathGeometry>.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Wie Sie aus den vorangehenden Beispielen sehen können, sind die beiden Mini-Sprachen sehr ähnlich. Es ist immer möglich, verwenden Sie eine <xref:System.Windows.Media.PathGeometry> in jeder Situation, in dem können Sie, eine <xref:System.Windows.Media.StreamGeometry>; daher sollten Sie verwenden? Verwenden einer <xref:System.Windows.Media.StreamGeometry> verwenden, wenn Sie den Pfad zu ändern, nachdem Sie erstellt wurde, benötigen eine <xref:System.Windows.Media.PathGeometry> , wenn Sie den Pfad ändern müssen.  
  
 Weitere Informationen zu den Unterschieden zwischen <xref:System.Windows.Media.PathGeometry> und <xref:System.Windows.Media.StreamGeometry> von Objekten finden Sie die [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Ein Hinweis zu Leerzeichen  
 Aus Platzgründen wird ein einzelnes Leerzeichen in den folgenden Syntaxabschnitten dargestellt, aber mehrere Leerzeichen sind auch zulässig, wo ein einzelnes Leerzeichen angezeigt wird.  
  
 Zwei Zahlen müssen nicht unbedingt durch ein Komma oder ein Leerzeichen getrennt werden, aber dies kann nur durchgeführt werden, wenn die resultierende Zeichenfolge eindeutig ist. Z. B. `2..3` ist eigentlich aus zwei Zahlen: "2". Und ".&3;". Auf ähnliche Weise `2-3` ist "2" und "3". Leerzeichen sind nicht erforderlich vor oder nach Befehlen, entweder.  
  
### <a name="syntax"></a>Syntax  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Syntax für das Attribut ein <xref:System.Windows.Media.StreamGeometry> besteht aus einem optionalen <xref:System.Windows.Media.FillRule> Wert und mindestens eine Beschreibung der Abbildung.  
  
|StreamGeometry XAML-Attributen|  
|-----------------------------------------|  
|`<`*object* *property* `="`[                                         `fillRule`]                                          `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
 Die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Syntax für das Attribut ein <xref:System.Windows.Media.PathFigureCollection> besteht aus mindestens Abbildung Beschreibungen.  
  
|PathFigureCollection XAML-Attributen|  
|-----------------------------------------------|  
|`<`*object* *property* `="` `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=fullName><br /><br /> Gibt an, ob die <xref:System.Windows.Media.StreamGeometry> verwendet die <xref:System.Windows.Media.FillRule> oder <xref:System.Windows.Media.FillRule><xref:System.Windows.Media.PathGeometry.FillRule%2A>.<br /><br /> -   `F0`Gibt die <xref:System.Windows.Media.FillRule> Füllungsregel.<br />-   `F1`Gibt die <xref:System.Windows.Media.FillRule> Füllungsregel.<br /><br /> Wenn Sie diesen Befehl auslassen, verwendet der untergeordnete Pfad das Standardverhalten <xref:System.Windows.Media.FillRule>. Wenn Sie diesen Befehl angeben, müssen Sie ihn zunächst platzieren.|  
|*figureDescription*|Eine Abbildung, bestehend aus einem Move-Befehl, draw-Befehlen und einer optionalen close-Befehl.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Ein Move-Befehl, der den Startpunkt der Abbildung angibt. Finden Sie unter der [Befehl verschieben](#themovecommand) Abschnitt.|  
|*drawCommands*|Eine oder mehrere zeichnen-Befehle, die den Inhalt der Abbildung beschreiben. Finden Sie unter der [Draw-Befehle](#drawcommands) Abschnitt.|  
|*closeCommand*|Einer optionalen close-Befehl, der Abbildung schließt. Finden Sie unter der [Close-Befehl](#closecommand) Abschnitt.|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a>Move-Befehl  
 Gibt den Startpunkt einer neuen Abbildung an.  
  
|Syntax|  
|------------|  
|`M`*StartPoint*<br /><br /> - oder -<br /><br /> `m`*StartPoint*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*Startpunkt*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Startpunkt einer neuen Abbildung.|  
  
 Ein großes `M` gibt an, dass `startPoint` ist ein absoluter Wert, einen Kleinbuchstaben `m` gibt an, dass `startPoint` um einen Offset zum vorherigen Punkt handelt oder um (0,0), falls keine vorhanden ist. Wenn Sie nach dem Move-Befehl mehrere Punkte auflisten, wird eine Linie zu diesen Punkten gezeichnet, obwohl Sie den Befehl Zeile angegeben.  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a>Draw-Befehle  
 Ein Draw-Befehl kann aus mehreren Shape-Befehlen bestehen. Die folgenden Befehle für Formen sind verfügbar: Linie, horizontale Linie, vertikale Linie, kubischen Bézierkurve, quadratische Bézier-Kurve, smooth kubischen Bézierkurve, glatte quadratische Bézier-Kurve und elliptischer Bogen.  
  
 Geben Sie jeden Befehl mit einem Großbuchstaben oder Kleinbuchstaben: Großbuchstaben absoluten Werten und deuten Kleinbuchstaben relative Werte: die Kontrollpunkte für dieses Segment sind abhängig vom Endpunkt des vorherigen Beispiels. Wenn Sie nacheinander mehrere Befehle desselben Typs eingeben, können Sie den Befehl Duplizieren Eintrag weglassen; beispielsweise `L 100,200 300,400` entspricht `L 100,200 L 300,400`. Die folgende Tabelle beschreibt die **verschieben** und **zeichnen** Befehle.  
  
### <a name="line-command"></a>In der Befehlszeile  
 Erstellt eine gerade Linie zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.                           `l 20 30`und `L 20,30` sind Beispiele für gültige **Zeile** Befehle.  
  
|Syntax|  
|------------|  
|`L`*Endpunkt*<br /><br /> - oder -<br /><br /> `l`*Endpunkt*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*Endpunkt*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Endpunkt der Linie.|  
  
### <a name="horizontal-line-command"></a>Befehl für eine horizontale Linie  
 Erstellt eine horizontale Linie zwischen dem aktuellen Punkt und dem angegebenen X-Koordinate.                          `H 90`ist ein Beispiel für einen Befehl gültige horizontale Linie.  
  
|Syntax|  
|------------|  
|`H`  *x*<br /><br /> - oder -<br /><br /> `h`  *x*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=fullName><br /><br /> Die X-Koordinate des Endpunkts der Linie.|  
  
### <a name="vertical-line-command"></a>Befehl für vertikale Linie  
 Erstellt eine vertikale Linie zwischen dem aktuellen Punkt und dem angegebenen y-Koordinate.                          `v 90`ist ein Beispiel für einen Befehl gültige vertikale Linie.  
  
|Syntax|  
|------------|  
|`V`  *y*<br /><br /> - oder -<br /><br /> `v`  *y*|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=fullName><br /><br /> Die y-Koordinate des Endpunkts der Linie.|  
  
### <a name="cubic-bezier-curve-command"></a>Befehl kubischen Bézierkurve  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt mithilfe von zwei angegebenen Kontrollpunkten ( `controlPoint`1 und `controlPoint`2).                          `C 100,200 200,400 300,200`ist ein Beispiel für einen gültigen Befehl.  
  
|Syntax|  
|------------|  
|`C` `controlPoint`1`controlPoint`2`endPoint`<br /><br /> - oder -<br /><br /> `c` `controlPoint`1`controlPoint`2`endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Die ersten Kontrollpunkts der Kurve, die beginnende Tangente der Kurve bestimmt.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Die zweiten Kontrollpunkts der Kurve, die die letzte Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="quadratic-bezier-curve-command"></a>Quadratische Bézier-Kurve-Befehl  
 Erstellt eine quadratische Bézier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt mithilfe des angegebenen Kontrollpunkts ( `controlPoint`).                          `q 100,200 300,200`ist ein Beispiel für einen gültigen Befehl für eine quadratische Bézier.  
  
|Syntax|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> - oder -<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Kontrollpunkt der Kurve, die die Start- und End Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Smooth kubischen Bézierkurve Befehl  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der erste Kontrollpunkt wird davon ausgegangen, dass die Reflektion des zweiten Kontrollpunkts des vorherigen Befehls ist relativ zum aktuellen Punkt ist. Ausgegangen Sie wenn es keinen vorherigen Befehl gibt oder der vorherige Befehl kein Befehl einer kubischen Bézierkurve oder eine glatte kubische Bézier-Kurve wurde, wird davon, dass der erste Kontrollpunkt mit dem aktuellen Stand ist. Der zweite Kontrollpunkt, der Kontrollpunkt für das Ende der Kurve, wird angegeben, indem `controlPoint`2. Z. B. `S 100,200 200,300` ist ein gültiger smooth kubische Bézier-Kurve Befehl.  
  
|Syntax|  
|------------|  
|`S` `controlPoint`2`endPoint`<br /><br /> - oder -<br /><br /> `s` `controlPoint`2`endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Kontrollpunkt der Kurve, die die letzte Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Glatte quadratische Bézier-Kurve Befehl  
 Erstellt eine quadratische Bézier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt. Der Kontrollpunkt wird davon ausgegangen, dass die Reflektion des Kontrollpunkts des vorherigen Befehls ist relativ zum aktuellen Zeitpunkt ist. Wenn kein vorherigen Befehl oder der vorherige Befehl Befehl einer quadratischen Bézierkurve oder eine glatte quadratische Bézier Kurve war, ist der Kontrollpunkt mit dem aktuellen Punkt.  
  
|Syntax|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> - oder -<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Kontrollpunkt der Kurve, die die Start- und die Tangente der Kurve bestimmt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Punkt, bis zu dem die Kurve gezeichnet wird.|  
  
### <a name="elliptical-arc-command"></a>Elliptischer Bogen-Befehl  
 Erstellt einen elliptischen Bogen zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.  
  
|Syntax|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> - oder -<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=fullName><br /><br /> Der X- und Y-Radius des Bogens.|  
|`rotationAngle`|<xref:System.Double?displayProperty=fullName><br /><br /> Die Drehung der Ellipse in Grad.|  
|`isLargeArcFlag`|Auf 1 festgelegt wird, wenn der Winkel des Bogens 180 Grad sein soll oder höher; andernfalls auf 0 festgelegt.|  
|`sweepDirectionFlag`|Auf 1 festgelegt, wenn der Bogen in einer Richtung mit positivem Winkel gezeichnet wird. andernfalls auf 0 festgelegt.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Der Punkt, bis zu dem der Bogen gezeichnet wird.|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a>Der Befehl "Schließen"  
 Beendet die aktuelle Abbildung und erstellt eine Linie, die den aktuellen Zeitpunkt auf den Startpunkt der Abbildung verbindet. Dieser Befehl erstellt eine Befehlszeile-Verknüpfung (Ecke) zwischen das letzte Segment und das erste Segment der Abbildung.  
  
|Syntax|  
|------------|  
|`Z`<br /><br /> - oder -<br /><br /> `z`|  
  
<a name="pointsyntax"></a>   
## <a name="point-syntax"></a>Punkt-Syntax  
 Beschreibt die x- und y-Koordinaten eines Punkts.  
  
|Syntax|  
|------------|  
|`x` `,` `y`<br /><br /> - oder -<br /><br /> `x` `y`|  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=fullName><br /><br /> Die X-Koordinate des Punkts.|  
|`y`|<xref:System.Double?displayProperty=fullName><br /><br /> Die y-Koordinate des Punkts.|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a>Spezielle Werte  
 Anstelle eines numerischen Standardwerts können Sie auch die folgenden speziellen Werte verwenden. Diese Werte sind Groß-und Kleinschreibung berücksichtigt.  
  
 Unendlich  
 Stellt <xref:System.Double.PositiveInfinity?displayProperty=fullName>.  
  
 minus unendlich  
 Stellt <xref:System.Double.NegativeInfinity?displayProperty=fullName>.  
  
 NaN  
 Stellt <xref:System.Double.NaN?displayProperty=fullName>.  
  
 Sie können auch die wissenschaftliche Schreibweise verwenden. Z. B. `+1.e17` ist ein gültiger Wert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.StreamGeometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.PathFigureCollection>   
 [Formen und die grundlegenden Funktionen zum Zeichnen in WPF (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Gewusst-wie-Themen](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)