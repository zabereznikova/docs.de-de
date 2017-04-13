---
title: "Priorit&#228;t von Abh&#228;ngigkeitseigenschaftswerten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Klassen, Eigentümer von Abhängigkeitseigenschaften"
  - "Abhängigkeitseigenschaften, Klassen als Eigentümer"
  - "Abhängigkeitseigenschaften, Metadaten"
  - "Metadaten, Abhängigkeitseigenschaften"
ms.assetid: 1fbada8e-4867-4ed1-8d97-62c07dad7ebc
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Priorit&#228;t von Abh&#228;ngigkeitseigenschaftswerten
<a name="introduction"></a> In diesem Thema wird beschrieben, wie die Funktionsweise des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Eigenschaftensystems den Wert einer [Abhängigkeitseigenschaft](GTMT) beeinflussen kann und mit welcher Priorität Aspekte des Eigenschaftensystems auf den effektiven Wert einer Eigenschaft angewendet werden.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht eines Consumers vorhandener Abhängigkeitseigenschaften für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Klassen auskennen und dass Sie das Thema [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) gelesen haben.  Um die Beispiele in diesem Thema verfolgen zu können, sollten Sie mit der Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und dem Schreiben von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen vertraut sein.  
  
<a name="intro"></a>   
## Das WPF\-Eigenschaftensystem  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem bietet eine leistungsstarke Methode, die Werte von Abhängigkeitseigenschaften durch eine Vielzahl von Faktoren bestimmen zu lassen, und ermöglicht so Features wie Eigenschaftenvalidierung in Echtzeit, dynamische Bindung und Benachrichtigung verwandter Eigenschaften über Änderungen an Werten anderer Eigenschaften.  Die genaue Reihenfolge und Logik zur Bestimmung der Abhängigkeitseigenschaftswerte ist relativ komplex.  Die Kenntnis dieser Reihenfolge hilft Ihnen, unnötige Eigenschafteneinstellungen zu vermeiden und zu verstehen, warum der Versuch, einen Abhängigkeitseigenschaftswert zu beeinflussen oder vorherzusehen, nicht zu dem erwarteten Ergebnis geführt hat.  
  
<a name="multiple_sets"></a>   
## Abhängigkeitseigenschaften können an mehreren Stellen festgelegt werden  
 Im folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Beispiel verfügt die gleiche Eigenschaft \(<xref:System.Windows.Controls.Control.Background%2A>\) über drei verschiedene Set\-Vorgänge, die den Wert beeinflussen können.  
  
 [!code-xml[PropertiesOvwSupport#DPPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#dpprecedence)]  
  
 Welche Farbe wird hier vermutlich angewendet – Rot, Grün oder Blau?  
  
 Mit Ausnahme von animierten Werten und Koersion werden lokale Eigenschaftensätze mit der höchsten Priorität festgelegt.  Wenn Sie einen Wert lokal festlegen, können Sie damit rechnen, dass der Wert sogar noch vor Stilen oder Steuerelementvorlagen berücksichtigt wird.  Im hier gezeigten Beispiel wird <xref:System.Windows.Controls.Control.Background%2A> lokal auf die Farbe Rot festgelegt.  Daher hat der in diesem Bereich definierte Stil bei der Festlegung des <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaftswerts nicht die höchste Priorität, obwohl es sich um einen impliziten Stil handelt, der andernfalls auf alle Elemente dieses Typs in dem Bereich angewendet würde.  Wenn Sie den lokalen Wert Rot von der Schaltflächeninstanz entfernen würden, hätte der Stil Vorrang, und die Schaltfläche würde den Hintergrundwert vom Stil erhalten.  Innerhalb des Stils haben Trigger Vorrang, sodass die Schaltfläche blau angezeigt würde, wenn sich der Mauszeiger darüber befindet, und andernfalls grün.  
  
<a name="listing"></a>   
## Liste der Abhängigkeitseigenschaftenpriorität  
 Nachstehend finden Sie die feste Reihenfolge, in der das Eigenschaftensystem die Laufzeitwerte von Abhängigkeitseigenschaften zuweist.  Die höchste Priorität steht an oberster Stelle in der Liste.  Diese Liste konkretisiert die unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) dargelegten Verallgemeinerungen.  
  
1.  **Eigenschaftensystemkoersion.** Ausführliche Informationen zur Koersion finden Sie im Abschnitt [Koersion, Animation und Basiswert](#animations) weiter unten in diesem Thema.  
  
2.  **Aktive Animationen oder Animationen mit einem Halteverhalten.** Um praktische Auswirkungen zu haben, muss eine Eigenschaftenanimation Vorrang vor dem \(unanimierten\) Basiswert haben können, selbst wenn dieser Wert lokal festgelegt wurde.  Ausführliche Informationen finden Sie im Abschnitt [Koersion, Animation und Basiswert](#animations) weiter unten in diesem Thema.  
  
3.  **Lokaler Wert.** Ein lokaler Wert kann bequem mithilfe der Wrappereigenschaft festgelegt werden, was auch der Festlegung als Attribut\- oder Eigenschaftenelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] entspricht, oder durch einen Aufruf der <xref:System.Windows.DependencyObject.SetValue%2A> [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] mithilfe einer Eigenschaft einer bestimmten Instanz.  Wenn Sie einen lokalen Wert mithilfe einer Bindung oder Ressource festlegen, hat dieser die gleiche Priorität wie ein direkter Wert.  
  
4.  **TemplatedParent\-Vorlageneigenschaften.** Ein Element verfügt über eine <xref:System.Windows.FrameworkElement.TemplatedParent%2A>, wenn es als Teil einer Vorlage erstellt wurde \(eine <xref:System.Windows.Controls.ControlTemplate> oder <xref:System.Windows.DataTemplate>\).  Ausführliche Informationen dazu, wann dies zutrifft, finden Sie im Abschnitt [TemplatedParent](#templatedparent) weiter unten in diesem Thema.  Innerhalb der Vorlage gilt die folgende Rangfolge:  
  
    1.  Trigger aus der <xref:System.Windows.FrameworkElement.TemplatedParent%2A>\-Vorlage.  
  
    2.  Eigenschaftensätze \(normalerweise über [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Attribute\) in der <xref:System.Windows.FrameworkElement.TemplatedParent%2A>\-Vorlage.  
  
5.  **Impliziter Stil.** Gilt nur für die `Style`\-Eigenschaft.  Die `Style`\-Eigenschaft wird durch jede Stilressource gefüllt, deren Schlüssel mit dem Typ des Elements übereinstimmt.  Die Stilressource muss entweder in der Seite oder in der Anwendung vorhanden sein. Die Suche nach einer impliziten Stilressource wird nicht in den Designs fortgesetzt.  
  
6.  **Stiltrigger.** Die Trigger in Stilen einer Seite oder Anwendung \(diese Stile können explizite oder implizite Stile sein, jedoch keine Standardstile, die eine geringere Priorität haben\).  
  
7.  **Vorlagentrigger.** Ein Trigger aus einer Vorlage innerhalb eines Stils oder eine direkt angewendete Vorlage.  
  
8.  **Stilsetter.** Werte von einem <xref:System.Windows.Setter> innerhalb von Stilen einer Seite oder Anwendung.  
  
9. **Standardstil \(Designstil\).** Ausführliche Informationen dazu, wann dies zutrifft und wie sich Designstile auf die Vorlagen in Designstilen beziehen, finden Sie im Abschnitt [Standardstile \(Designstile\)](#themestyles) weiter unten in diesem Thema.  Innerhalb eines Standardstils gilt die folgende Rangfolge:  
  
    1.  Aktive Trigger im Designstil.  
  
    2.  Setter im Designstil.  
  
10. **Vererbung.** Einige Abhängigkeitseigenschaften vererben ihre Werte von übergeordneten Elementen an untergeordnete Elemente, sodass sie nicht für jedes Element in einer Anwendung speziell festgelegt werden müssen.  Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
11. **Standardwert von Metadaten für die Abhängigkeitseigenschaft.** Eine Abhängigkeitseigenschaft kann einen Standardwert besitzen, der durch die Eigenschaftensystemregistrierung dieser Eigenschaft festgelegt wird.  Außerdem haben abgeleitete Klassen, die eine Abhängigkeitseigenschaft erben, die Möglichkeit zum Überschreiben der Metadaten \(einschließlich des Standardwerts\) auf Typbasis.  Weitere Informationen finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  Da die Vererbung vor dem Standardwert überprüft wird, hat bei einer geerbten Eigenschaft der Standardwert eines übergeordneten Elements Vorrang vor dem eines untergeordneten Elements.  Wenn eine vererbbare Eigenschaft nicht festgelegt ist, wird folglich der für das Stamm\- oder übergeordnete Element angegebene Standardwert anstelle des Standardwerts für das untergeordnete Element verwendet.  
  
<a name="templatedparent"></a>   
## TemplatedParent  
 TemplatedParent wird als Prioritätselement nicht auf Elementeigenschaften angewendet, die Sie in einer herkömmlichen Markupsprache direkt deklarieren.  Das TemplatedParent\-Konzept ist nur für untergeordnete Elemente in einer visuellen Struktur verfügbar, die durch Anwendung der Vorlage erstellt werden.  Wenn das Eigenschaftensystem die <xref:System.Windows.FrameworkElement.TemplatedParent%2A>\-Vorlage nach einem Wert durchsucht, verwendet es hierfür die Vorlage, mit der das Element erstellt wurde.  Die Eigenschaftswerte aus der <xref:System.Windows.FrameworkElement.TemplatedParent%2A>\-Vorlage verhalten sich normalerweise, als wären sie als lokaler Wert für das untergeordnete Element festgelegt worden, doch diese im Vergleich zum lokalen Wert geringere Priorität kommt dadurch zustande, dass die Vorlagen möglicherweise freigegeben sind.  Ausführliche Informationen finden Sie unter <xref:System.Windows.FrameworkElement.TemplatedParent%2A>.  
  
<a name="style_property"></a>   
## Die Style\-Eigenschaft  
 Die zuvor beschriebene Suchreihenfolge gilt für alle möglichen Abhängigkeitseigenschaften mit Ausnahme der <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft.  Die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft ist insofern einmalig, dass ihr selbst kein Stil zugewiesen werden kann. Die Prioritätselemente 5 bis 8 treffen also nicht zu.  Außerdem wird davon abgeraten, eine Animation oder Koersion von <xref:System.Windows.FrameworkElement.Style%2A> vorzunehmen \(für die Animation von <xref:System.Windows.FrameworkElement.Style%2A> wäre eine benutzerdefinierte Animationsklasse erforderlich\).  Dadurch bleiben drei Möglichkeiten, die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft festzulegen:  
  
-   **Expliziter Stil.** Die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft wird direkt festgelegt.  In den meisten Szenarios wird der Stil nicht inline definiert, sondern anhand eines expliziten Schlüssels als Ressource referenziert.  In diesem Fall verhält sich die Style\-Eigenschaft wie ein lokaler Wert \(Prioritätselement 3\).  
  
-   **Impliziter Stil.** Die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft wird nicht direkt festgelegt.  <xref:System.Windows.FrameworkElement.Style%2A> ist jedoch auf einer bestimmten Ebene in der Ressourcensuchsequenz \(Seite, Anwendung\) vorhanden und wird mithilfe eines Ressourcenschlüssels verschlüsselt, der dem Typ entspricht, auf den der Stil angewendet werden soll.  In diesem Fall verhält sich die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft gemäß der Priorität, die in der Rangfolge Prioritätselement 5 entspricht.  Dieser Zustand kann bestimmt werden, indem <xref:System.Windows.DependencyPropertyHelper> auf die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft angewendet wird und in den Ergebnissen nach <xref:System.Windows.BaseValueSource> gesucht wird.  
  
-   **Standardstil**, auch als **Designstil** bezeichnet. Die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft wird nicht direkt festgelegt und hat bis zur Laufzeit den Wert `null`.  In diesem Fall wird der Stil durch die Designauswertung zur Laufzeit bestimmt, die Teil des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Darstellungsmoduls ist.  
  
 Bei impliziten Stilen außerhalb von Designs muss der Typ genau übereinstimmen – eine abgeleitete `MyButton` `Button`\-Klasse verwendet keinen impliziten Stil für `Button`.  
  
<a name="themestyles"></a>   
## Standardstile \(Designstile\)  
 Jedes Steuerelement, das mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellt wird, verfügt über einen Standardstil.  Dieser Standardstil kann je nach Design variieren, weshalb er mitunter auch als Designstil bezeichnet wird.  
  
 Die wichtigsten Informationen, die ein Standardstil für ein Steuerelement enthält, liefert die Steuerelementvorlage, die im Designstil als Setter für die <xref:System.Windows.Controls.Control.Template%2A>\-Eigenschaft vorhanden ist.  Wenn Standardstile keine Vorlagen enthalten würden, hätte ein Steuerelement, das keine benutzerdefinierte Vorlage als Teil eines benutzerdefinierten Stils besitzt, überhaupt keine visuelle Darstellung.  Die Vorlage aus dem Standardstil verleiht der visuellen Darstellung eines Steuerelements eine grundlegende Struktur und definiert die Verbindungen zwischen Eigenschaften, die in der visuellen Struktur der Vorlage und der entsprechenden Steuerelementklasse definiert sind.  Jedes Steuerelement macht einen Satz von Eigenschaften verfügbar, die die visuelle Darstellung des Steuerelements beeinflussen können, ohne die Vorlage vollständig zu ersetzen.  Betrachten Sie z. B. die visuelle Standarddarstellung eines <xref:System.Windows.Controls.Primitives.Thumb>\-Steuerelements, das eine Komponente von <xref:System.Windows.Controls.Primitives.ScrollBar> ist.  
  
 Ein <xref:System.Windows.Controls.Primitives.Thumb> verfügt über bestimmte anpassbare Eigenschaften.  Die Standardvorlage für ein <xref:System.Windows.Controls.Primitives.Thumb> liefert eine grundlegende Struktur bzw. eine visuelle Struktur mit mehreren geschachtelten <xref:System.Windows.Controls.Border>\-Komponenten zum Erstellen einer Abschrägung.  Wenn eine Eigenschaft, die Teil der Vorlage ist, zur Anpassung durch die <xref:System.Windows.Controls.Primitives.Thumb>\-Klasse verfügbar gemacht werden soll, muss diese Eigenschaft mithilfe einer [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) innerhalb der Vorlage verfügbar gemacht werden.  Im Fall von <xref:System.Windows.Controls.Primitives.Thumb> haben verschiedene Eigenschaften dieser Rahmen eine Vorlagenbindung an Eigenschaften wie <xref:System.Windows.Controls.Border.Background%2A> oder <xref:System.Windows.Controls.Border.BorderThickness%2A> gemeinsam.  Bestimmte andere Eigenschaften oder visuelle Gestaltungen sind jedoch in der Steuerelementvorlage fest codiert oder an Werte gebunden, die direkt aus dem Design stammen, und können nicht geändert werden, außer die gesamte Vorlage wird ersetzt.  Im Allgemeinen kann eine Eigenschaft, die aus einem auf Vorlagen basierenden übergeordneten Element stammt und nicht mithilfe einer Vorlagenbindung verfügbar gemacht wird, nicht durch Stile angepasst werden, da sie nicht ohne Weiteres als Ziel verwendet werden kann.  Allerdings kann diese Eigenschaft durch Vererbung von Eigenschaftswerten in der angewendeten Vorlage oder durch den Standardwert beeinflusst werden.  
  
 Die Definitionen von Designstilen verwenden einen Typ als Schlüssel.  Wenn jedoch Designs auf eine bestimmte Elementinstanz angewendet werden, wird die Designsuche für diesen Typ durch Überprüfen der <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>\-Eigenschaft für ein Steuerelement ausgeführt.  Dies steht im Gegensatz zur Verwendung des Literaltyps, wie bei impliziten Stilen.  Der Wert von <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> würde an abgeleitete Klassen vererbt, auch wenn der Implementierer ihn nicht geändert hätte \(die beabsichtige Methode zum Ändern der Eigenschaft besteht nicht darin, sie auf der Eigenschaftenebene zu überschreiben, sondern ihren Standardwert in den Eigenschaftenmetadaten zu ändern\).  Diese Dereferenzierung ermöglicht es Basisklassen, die Designstile für abgeleitete Elemente zu definieren, die sonst über keinen Stil verfügen \(und die, was noch wichtiger ist, keine Vorlage in diesem Stil besitzen und daher überhaupt keine visuelle Standarddarstellung hätten\).  Folglich können Sie `MyButton` von <xref:System.Windows.Controls.Button> ableiten und erhalten trotzdem die <xref:System.Windows.Controls.Button>\-Standardvorlage.  Wenn Sie der Autor des `MyButton`\-Steuerelements wären und sein Verhalten ändern wollten, könnten Sie die Metadaten für die <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>\-Abhängigkeitseigenschaft von `MyButton` überschreiben, sodass ein anderer Schlüssel zurückgegeben wird, und anschließend die relevanten Designstile definieren, einschließlich einer Vorlage für `MyButton`, die Sie mit dem `MyButton`\-Steuerelement bereitstellen müssen.  Ausführliche Informationen über Designs, Stile und das Erstellen von Steuerelementen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="resources"></a>   
## Dynamische Ressourcenverweise und Bindung  
 Bei dynamischen Ressourcenverweisen und Bindungsvorgängen wird die Priorität des Orts berücksichtigt, an dem sie festgelegt werden.  Beispielsweise verhält sich eine dynamische Ressource, die auf einen lokalen Wert angewendet wird, gemäß Prioritätselement 3, eine Bindung für einen Eigenschaftensetter in einem Designstil gemäß Prioritätselement 9 usw.  Da dynamische Ressourcenverweise und Bindungsvorgänge in der Lage sein müssen, Werte vom Laufzeitzustand der Anwendung abzurufen, hat dies zur Folge, dass sich die eigentliche Bestimmung der Priorität von Eigenschaftswerten für eine bestimmte Eigenschaft auch auf die Laufzeit erstreckt.  
  
 Dynamische Ressourcenverweise sind streng genommen nicht Teil des Eigenschaftensystems, sondern verfügen über ihre eigene Suchreihenfolge, die mit der oben aufgeführten Rangfolge interagiert.  Ausführliche Informationen über diese Rangfolge finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  Im Wesentlichen lässt sich diese Rangfolge wie folgt zusammenfassen: Element, Seitenstamm, Anwendung, Design, System.  
  
 Für dynamische Ressourcen und Bindungen gilt die Priorität des Orts, an dem sie festgelegt wurden, der Wert wird jedoch verzögert.  Wenn Sie eine dynamische Ressource oder eine Bindung auf einen lokalen Wert festlegen, führt dies daher dazu, dass die dynamische Ressource oder Bindung durch jede Änderung am lokalen Wert vollständig ersetzt wird.  Die dynamische Ressource oder Bindung kann auch dann nicht wiederhergestellt werden, wenn Sie die <xref:System.Windows.DependencyObject.ClearValue%2A>\-Methode aufrufen, um den lokal festgelegten Wert zu löschen.  Wenn Sie <xref:System.Windows.DependencyObject.ClearValue%2A> für eine Eigenschaft aufrufen, die über eine dynamische Ressource oder Bindung verfügt \(ohne einen lokalen Literalwert\), wird diese ebenfalls durch den <xref:System.Windows.DependencyObject.ClearValue%2A>\-Aufruf gelöscht.  
  
<a name="setcurrentvalue"></a>   
## SetCurrentValue  
 Die <xref:System.Windows.DependencyObject.SetCurrentValue%2A>\-Methode ist eine weitere Möglichkeit zum Festlegen einer Eigenschaft, bei der die Priorität jedoch nicht berücksichtigt wird.  Stattdessen können Sie mit <xref:System.Windows.DependencyObject.SetCurrentValue%2A> den Wert einer Eigenschaft ändern, ohne die Quelle eines vorherigen Werts zu überschreiben.  Sie können <xref:System.Windows.DependencyObject.SetCurrentValue%2A> verwenden, wenn Sie einen Wert festlegen möchten, der keine Priorität vor einem lokalen Wert haben soll.  Wenn eine Eigenschaft z. B. durch einen Trigger festgelegt wird, und ihr wird anschließend über <xref:System.Windows.DependencyObject.SetCurrentValue%2A> ein anderer Wert zugewiesen, berücksichtigt das Eigenschaftensystem den Trigger weiterhin, und die Eigenschaft wird geändert, wenn die Aktion des Triggers ausgeführt wird.  <xref:System.Windows.DependencyObject.SetCurrentValue%2A> ermöglicht es Ihnen, den Wert der Eigenschaft zu ändern, ohne ihr eine Quelle mit einer höheren Priorität zuzuweisen.  Entsprechend können Sie <xref:System.Windows.DependencyObject.SetCurrentValue%2A> verwenden, um den Wert einer Eigenschaft zu ändern, ohne eine Bindung zu überschreiben.  
  
<a name="animations"></a>   
## Koersion, Animation und Basiswert  
 Koersion und Animation werden beide für einen Wert ausgeführt, der in diesem [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] als "Basiswert" bezeichnet wird.  Der Basiswert ist demnach ein beliebiger Wert, der bestimmt wird, indem die Elemente so lange nach oben hin ausgewertet werden, bis Element 2 erreicht wird.  
  
 Für eine Animation kann sich der Basiswert auf den animierten Wert auswirken, wenn die Animation für bestimmte Verhalten keine Von\-Bis\-Werte angibt oder nach Beendigung absichtlich auf den Basiswert zurückgesetzt wird.  Um dies in der Praxis zu sehen, führen Sie das [Beispiel für From, To, and By\-Animationszielwerte](http://go.microsoft.com/fwlink/?LinkID=159988) aus.  Versuchen Sie, die lokalen Werte für die Rechteckhöhe im Beispiel so festzulegen, dass sich der lokale Anfangswert von jedem Von\-Wert in der Animation unterscheidet.  Sie werden feststellen, dass die Animationen sofort unter Verwendung der Von\-Werte starten und daraufhin den Basiswert ersetzen.  Mit Stop <xref:System.Windows.Media.Animation.FillBehavior> kann angegeben werden, dass nach Beendigung der Animation der Wert zurückgegeben werden soll, der vor der Animation gefunden wurde.  Anschließend wird zur Bestimmung des Basiswerts die normale Rangfolge verwendet.  
  
 Auf eine einzige Eigenschaft können mehrere Animationen angewendet werden, von denen jede möglicherweise von verschiedenen Punkten in der Wertrangfolge definiert wurde.  Diese Animationen wenden jedoch nicht einfach die Animation der höheren Rangfolge an, sondern fassen ihre Werte zusammen.  Dies ist davon abhängig, wie die Animationen genau definiert wurden und welchem Typ der animierte Wert entspricht.  Weitere Informationen über das Animieren von Eigenschaften finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Koersion wird auf der höchsten Ebene angewendet.  Selbst eine bereits ausgeführte Animation kann der Wertkoersion unterliegen.  Bestimmte vorhandene Abhängigkeitseigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über eine integrierte Koersion.  Für eine benutzerdefinierte Abhängigkeitseigenschaft definieren Sie das Koersionsverhalten, indem Sie einen <xref:System.Windows.CoerceValueCallback> schreiben und den Rückruf beim Erstellen der Eigenschaft als Teil der Metadaten übergeben.  Sie können auch das Koersionsverhalten einer vorhandenen Eigenschaft überschreiben, indem Sie die Metadaten für diese Eigenschaft in einer abgeleiteten Klasse überschreiben.  Die Koersion interagiert dahingehend mit dem Basiswert, dass die Koersionseinschränkungen so angewendet werden, wie sie augenblicklich vorliegen, doch der Basiswert weiterhin beibehalten wird.  Wenn Koersionseinschränkungen also im Nachhinein aufgehoben werden, gibt die Koersion den Wert zurück, der dem Basiswert am nächsten kommt. Außerdem verliert die Koersion möglicherweise ihren Einfluss auf eine Eigenschaft, sobald alle Einschränkungen aufgehoben wurden.  Weitere Informationen über das Koersionsverhalten finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
<a name="triggers"></a>   
## Triggerverhalten  
 Steuerelemente definieren als Teil ihres Standardstils in Designs oft das Verhalten von Triggern.  Durch das Festlegen lokaler Eigenschaften für Steuerelemente wird möglicherweise verhindert, dass die Trigger auf benutzergesteuerte Ereignisse reagieren können, entweder bezüglich der Darstellung oder des Verhaltens.  Die häufigste Verwendung von Eigenschaftentriggern sind Steuerelement\- oder Zustandseigenschaften wie <xref:System.Windows.Controls.Primitives.Selector.IsSelected%2A>.  Wenn z. B. eine <xref:System.Windows.Controls.Button> deaktiviert wird \(der Trigger für <xref:System.Windows.UIElement.IsEnabled%2A> ist `false`\), bestimmt der <xref:System.Windows.Controls.Control.Foreground%2A>\-Wert im Designstil, dass das Steuerelement abgeblendet wird.  Wenn Sie jedoch einen lokalen <xref:System.Windows.Controls.Control.Foreground%2A>\-Wert festgelegt haben, wird die abgeblendete Darstellung durch den lokalen Eigenschaftensatz überschrieben, sogar in diesem Eigenschaftentriggerszenario.  Beim Festlegen von Werten für Eigenschaften, deren Triggerverhalten auf Designebene definiert ist, sollten Sie vorsichtig vorgehen und sicherstellen, dass die gewünschte Benutzerfreundlichkeit dieses Steuerelements nicht unnötig beeinträchtigt wird.  
  
<a name="clearvalue"></a>   
## "ClearValue" und Wertpriorität  
 Die <xref:System.Windows.DependencyObject.ClearValue%2A>\-Methode ist eine hilfreiche Möglichkeit zum Löschen von lokal angewendeten Werten einer [Abhängigkeitseigenschaft](GTMT), die für ein Element festgelegt ist.  Das Aufrufen von <xref:System.Windows.DependencyObject.ClearValue%2A> bietet jedoch keine Garantie dafür, dass der Standardwert, der bei der Eigenschaftenregistrierung in Metadaten festgelegt wurde, der neue effektive Wert ist.  Alle anderen an der Wertpriorität beteiligten Elemente sind weiterhin aktiv.  Nur der lokal festgelegte Wert wurde aus der Prioritätsrangfolge entfernt.  Wenn Sie z. B. <xref:System.Windows.DependencyObject.ClearValue%2A> für eine Eigenschaft aufrufen, die auch durch einen Designstil festgelegt wird, wird anstelle des metadatenbasierten Standardwerts der Designwert als neuer Wert angewendet.  Wenn Sie alle am Eigenschaftswert beteiligten Elemente aus dem Prozess entfernen und den Wert auf den Standardwert der registrierten Metadaten festlegen möchten, können Sie diesen Standardwert durch Abfragen der Metadaten für die Abhängigkeitseigenschaft ermitteln und anschließend die Eigenschaft mithilfe des Standardwerts durch einen Aufruf von <xref:System.Windows.DependencyObject.SetValue%2A> lokal festlegen.  
  
## Siehe auch  
 <xref:System.Windows.DependencyObject>   
 <xref:System.Windows.DependencyProperty>   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)