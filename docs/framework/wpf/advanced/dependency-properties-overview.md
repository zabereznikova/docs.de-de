---
title: Übersicht über Abhängigkeitseigenschaften
description: Eine Eigenschaft, die durch die WPF-Eigenschaftensystem gesichert wird, wird als eine Abhängigkeitseigenschaft bezeichnet. In dieser Übersicht werden die WPF-Eigenschaftensystem und die Funktionen einer Abhängigkeitseigenschaft.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], attached
- properties [WPF], overview
- styles [WPF]
- attached properties [WPF]
- data binding [WPF]
- dependency properties [WPF]
- resources [WPF], references to
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
ms.openlocfilehash: 196e858c52c06c96d652209e86039bfcc81a785a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dependency-properties-overview"></a>Übersicht über Abhängigkeitseigenschaften

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine Reihe von Diensten, die zum Erweitern der Funktionalität einer [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaft verwendet werden können. Zusammen werden diese Dienste normalerweise als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystem bezeichnet. Eine Eigenschaft, die von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaft unterstützt wird, wird als Abhängigkeitseigenschaft bezeichnet. In dieser Übersicht wird das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystem und die Funktionen einer Abhängigkeitseigenschaft beschrieben. Dies schließt die Verwendung vorhandener Abhängigkeitseigenschaften in XAML und Code ein. In dieser Übersicht werden auch spezielle Aspekte von Abhängigkeitseigenschaften wie die Metadaten von Abhängigkeitseigenschaften sowie die Erstellung einer eigenen Abhängigkeitseigenschaft in einer benutzerdefinierten Klasse eingeführt.

## <a name="prerequisites"></a>Erforderliche Komponenten
In diesem Thema wird vorausgesetzt, dass Sie über einige grundlegende Kenntnisse der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] und der objektorientierten Programmierung verfügen. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vertraut sein und wissen, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen geschrieben werden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="dependency-properties-and-clr-properties"></a>Abhängigkeitseigenschaften und CLR-Eigenschaften
 Eigenschaften werden in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in der Regel als [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaften verfügbar gemacht. Grundsätzlich können Sie direkt mit diesen Eigenschaften direkt interagieren, ohne zu wissen, dass sie als Abhängigkeitseigenschaft implementiert werden. Sie sollten aber mit einigen oder allen Funktionen des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems vertraut sein, damit Sie sie nutzen können.

Abhängigkeitseigenschaften dienen der Berechnung des Werts einer Eigenschaft anhand des Werts von anderen Eingaben. Zu diese anderen Eingaben gehören Systemeigenschaften wie Designs und die Benutzervoreinstellung, Feststellungsmechanismen für Just-In-Time-Eigenschaft wie die Datenbindung und Animationen/Storyboards, mehrfach verwendbare Vorlagen, z.B. Ressourcen und Stile, oder Werte, die über übergeordnete und untergeordnete Beziehungen mit anderen Elementen in der Elementstruktur bekannt sind. Darüber hinaus kann eine Abhängigkeitseigenschaft implementiert werden, um ein selbstständige Überprüfung, Standardwerte, Rückrufe, die Änderungen an anderen Eigenschaften überwachen, sowie ein System bereitzustellen, das Eigenschaftswerte auf Grundlage potenzieller Laufzeitinformationen erzwingen kann. Abgeleitete Klassen können auch einige spezifische Merkmale einer vorhandenen Eigenschaft durch Überschreiben von Metadaten für Abhängigkeitseigenschaften ändern, anstatt die tatsächliche Implementierung der vorhandenen Eigenschaften zu überschreiben oder neue Eigenschaften zu erstellen.

Anhand der SDK-Referenz können Sie ermitteln, welche Eigenschaft eine Abhängigkeitseigenschaft ist, wenn diese im Abschnitt „Informationen zur Abhängigkeitseigenschaft“ auf der verwalteten Referenzseite für diese Eigenschaft vorhanden ist. Der Abschnitt Informationen zur Abhängigkeitseigenschaft enthält einen Link zu der <xref:System.Windows.DependencyProperty> Bezeichner für die Abhängigkeitseigenschaft Felds, und schließt auch eine Liste der Metadatenoptionen, die für diese Eigenschaft, außerkraftsetzungsinformationen pro-Klasse und andere Details festgelegt werden.

## <a name="dependency-properties-back-clr-properties"></a>Abhängigkeitseigenschaften sichern CLR-Eigenschaften
Abhängigkeitseigenschaften und das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystem erweitern die Funktionalität von Eigenschaften durch die Bereitstellung eines Typs, der eine Eigenschaft als eine alternative Implementierung zum standardmäßigen Muster unterstützt, bei dem die Eigenschaft mit einem privaten Feld unterstützt wird. Der Name dieses Typs ist <xref:System.Windows.DependencyProperty>. Der andere wichtige Typ, definiert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaftensystem ist <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject> definiert die Basisklasse, die registrieren und eine Abhängigkeitseigenschaft besitzen kann.

Es folgt eine Zusammenfassung der Terminologie, die in dieser [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]-Dokumentation bei der Beschreibung von Abhängigkeitseigenschaften verwendet wird:

- **Abhängigkeitseigenschaft:** eine Eigenschaft, die durch gesichert wird eine <xref:System.Windows.DependencyProperty>.

- **Ein Abhängigkeitseigenschaftbezeichner:** ein <xref:System.Windows.DependencyProperty> -Instanz, die als Rückgabewert abgerufen werden, wenn Sie eine Abhängigkeitseigenschaft zu registrieren und dann als ein statischer Member einer Klasse gespeichert. Dieser Bezeichner wird als Parameter für viele der [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] verwendet, die mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftenssystem intergieren.

- **CLR-Wrapper:** Die tatsächlichen Implementierungen zum Abrufen und Festlegen für die Eigenschaft. Diese Implementierungen Bezeichner für die Abhängigkeitseigenschaft integrieren, indem Sie diesen in der <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> Aufrufe auf diese Weise bietet die Sicherung für die Eigenschaft mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaftensystem.

Das folgende Beispiel definiert die `IsSpinning` Abhängigkeitseigenschaft, und zeigt die Beziehung von der <xref:System.Windows.DependencyProperty> Bezeichner, der die Eigenschaft, die er gesichert wird.

[!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
[!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
  
Die Namenskonvention der Eigenschaft und die unterstützenden <xref:System.Windows.DependencyProperty> Feld wichtig ist. Der Name des Felds ist immer der Name der Eigenschaft, die mit dem Suffix `Property` endet. Weitere Informationen zu dieser Konvention und die Gründe dafür finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  

## <a name="setting-property-values"></a>Festlegen von Eigenschaftswerten
Sie können Eigenschaften sowohl im Code als auch in XAML festlegen.

### <a name="setting-property-values-in-xaml"></a>Festlegen von Eigenschaftswerten in XAML 
Im folgende XAML-Beispiel wird die Hintergrundfarbe einer Schaltfläche als Rot dargestellt. Dieses Beispiel veranschaulicht eine Situation, in denen die einfache Zeichenfolgenwert für ein Attribut für die Verwendung von XAML-Typ konvertiert werden, indem der WPF XAML-Parser in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Typ (ein <xref:System.Windows.Media.Color>, über eine <xref:System.Windows.Media.SolidColorBrush>) im generierten Code.

[!code-xaml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]

XAML unterstützt eine Vielzahl an Syntaxformen zum Festlegen von Eigenschaften. Welche Syntax für eine bestimmte Eigenschaft verwendet wird, hängt vom Werttyp ab, den eine Eigenschaft verwendet, sowie von anderen Faktoren wie dem Vorhandensein eines Typkonverters. Weitere Informationen zur XAML-Syntax zum Festlegen von Eigenschaften finden Sie unter [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) und [Ausführliche Erläuterung der XAML-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).

Im folgende XAML-Beispiel wird ein Beispiel für eine Syntax ohne Attribut und einen anderen Hintergrund für eine Schaltfläche. Diesmal wird nicht einfach eine Volltonfarbe, sondern der Hintergrund auf ein Bild mit einem Element festgelegt, das dieses Bild und die Bildquelle angegeben als Attribut des geschachtelten Elements darstellt. Dies ist ein Beispiel für Eigenschaftenelementsyntax.

[!code-xaml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]

### <a name="setting-properties-in-code"></a>Festlegen von Eigenschaften im code
 Das Festlegen von Abhängigkeitseigenschaften im Code geschieht in der Regel über einen Aufruf der festgelegten Implementierung, die vom [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Wrapper verfügbar gemacht wird.

[!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
[!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]

Das Abrufen eines Eigenschaftswerts besteht auch im Grunde aus einem Aufruf der Implementierung zum Abrufen des Wrappers:

[!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]

Sie können auch im Eigenschaftensystem Aufrufen [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> direkt. Dies ist üblicherweise nicht erforderlich, wenn Sie vorhandene Eigenschaften verwenden (die Wrapper sind besser geeignet und stellen eine bessere Verfügbarkeit der Eigenschaft für Entwicklungswerkzeuge bereit). Das Aufrufen von [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] ist jedoch geeignet für bestimmte Szenarios.

Eigenschaften können auch in XAML festgelegt und später über den Code (über die CodeBehind-Datei) darauf zugegriffen werden. Weitere Informationen finden Sie unter [CodeBehind und XAML in WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

## <a name="property-functionality-provided-by-a-dependency-property"></a>Eigenschaftenfunktionalität, die von einer Abhängigkeitseigenschaft bereitgestellt
Eine Abhängigkeitseigenschaft stellt Funktionen bereit, die die Funktionalität einer Eigenschaft gegenüber einer Eigenschaft übertreffen, die durch ein Feld unterstützt wird. Häufig stellen diese Funktionalitäten eine bestimmte Funktion von allgemeinen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen dar oder unterstützen sie:

- [Ressourcen](#resources)

- [Datenbindung](#data-binding)

- [Stile](#styles)

- [Animationen](#animations)

- [Überschreiben von Metadaten](#metadata-overrides)

- [Vererbung von Eigenschaftswerten](#property-value-inheritance)

- [WPF-Designer-Integration](#wpf-designer-integration)

### <a name="resources"></a>Ressourcen
Ein Wert einer Abhängigkeitseigenschaft kann durch Verweisen auf eine Ressource festgelegt werden. Ressourcen werden in der Regel als der `Resources`-Eigenschaftswert eines Seitenstammelements oder der Anwendung angegeben (diese Positionen ermöglichen den einfachsten Zugriff auf die Ressource). Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Media.SolidColorBrush> Ressource.

[!code-xaml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]

Nachdem die Ressource definiert wurde, können Sie auf die Ressource verweisen und einen Eigenschaftswert bereitstellen:

[!code-xaml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]

Auf diese spezielle Ressource wird als ein [DynamicResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) verwiesen (in WPF-XAML können Sie entweder einen statischen oder dynamischen Ressourcenverweis verwenden). Um einen dynamischen Ressourcenverweis zu verwenden, müssen Sie auf eine Abhängigkeitseigenschaft festlegen. Daher wird vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystem insbesondere die Verwendung dynamischer Ressourcenverweise ermöglicht. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).

> [!NOTE]
> Ressourcen werden als ein lokaler Wert behandelt. Wenn Sie also einen anderen lokalen Wert festgelegt haben, beseitigen Sie den Verweis auf die Ressource. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

### <a name="data-binding"></a>Datenbindung
Eine Abhängigkeitseigenschaft kann über die Datenbindung auf einen Wert verweisen. Die Datenbindung funktioniert über einen bestimmten Markuperweiterungssyntax in XAML oder <xref:System.Windows.Data.Binding> Objekt im Code. Mit der Datenbindung wird die letzte Bestimmung des Eigenschaftswerts bis zur Laufzeit zurückgestellt. Zu diesem Zeitpunkt wird der Wert aus einer Datenquelle abgerufen.

Im folgenden Beispiel wird die <xref:System.Windows.Controls.ContentControl.Content%2A> -Eigenschaft für eine <xref:System.Windows.Controls.Button>, mit einer Bindung in XAML deklariert. Die Bindung verwendet einen geerbten Datenkontext und eine <xref:System.Windows.Data.XmlDataProvider> -Datenquelle (nicht dargestellt). Die Bindung selbst gibt die gewünschte Quelleigenschaft von <xref:System.Windows.Data.Binding.XPath%2A> innerhalb der Datenquelle.

[!code-xaml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]

> [!NOTE]
> Bindungen werden als ein lokaler Wert behandelt. Wenn Sie also einen anderen lokalen Wert festgelegt haben, beseitigen Sie die Bindung. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

Abhängigkeitseigenschaften, oder die <xref:System.Windows.DependencyObject> Klasse, die nicht systemeigen unterstützen <xref:System.ComponentModel.INotifyPropertyChanged> Rahmen, der Benachrichtigungen über Änderungen in erzeugt <xref:System.Windows.DependencyObject> Eigenschaftswert für die Bindung Datenvorgänge Datenquelle. Weitere Informationen zum Erstellen von Eigenschaften für die Datenbindung, die Änderungen an einem Datenbindungsziel melden können, finden Sie unter [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).

### <a name="styles"></a>Stile
Stile und Vorlagen sind zwei Hauptgründe für die Verwendung von Abhängigkeitseigenschaften. Stile eignen sich besonders für das Festlegen von Eigenschaften, die die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Anwendung definieren. Stile werden in XAML in der Regel als Ressourcen definiert. Stile interagieren mit dem Eigenschaftensystem, weil sie normalerweise sowohl „Setter“ für bestimmte Eigenschaften als auch „Trigger“ enthalten, die einen Eigenschaftswert basierend auf dem Echtzeitwert einer anderen Eigenschaft ändern.

Im folgende Beispiel wird ein sehr einfachen Stil erstellt (definiert die in eine <xref:System.Windows.FrameworkElement.Resources%2A> Wörterbuch vorhanden ist, nicht angezeigt), gilt Sie diesem Format direkt für die <xref:System.Windows.FrameworkElement.Style%2A> -Eigenschaft für eine <xref:System.Windows.Controls.Button>. Der Setter im Stil legt die <xref:System.Windows.Controls.Control.Background%2A> -Eigenschaft für eine formatierte <xref:System.Windows.Controls.Button> in Grün.

[!code-xaml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]

[!code-xaml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]

Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).

### <a name="animations"></a>Animationen
Abhängigkeitseigenschaften können animiert werden. Wenn eine Animation angewendet wurde und ausgeführt wird, verfügt der animierte Wert über eine höhere Priorität als alle anderen Werte (z.B. ein lokaler Wert), über die die Eigenschaft sonst verfügt.

Das folgende Beispiel erstellt eine Animation der <xref:System.Windows.Controls.Control.Background%2A> auf eine <xref:System.Windows.Controls.Button> Eigenschaft (technisch gesehen der <xref:System.Windows.Controls.Control.Background%2A> wird mithilfe der Eigenschaftenelementsyntax ein leeres animiert <xref:System.Windows.Media.SolidColorBrush> als die <xref:System.Windows.Controls.Control.Background%2A>, die <xref:System.Windows.Media.SolidColorBrush.Color%2A> -Eigenschaft dieses <xref:System.Windows.Media.SolidColorBrush> ist die Eigenschaft, die direkt animiert wird).

[!code-xaml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]

Weitere Informationen zur Animation von Eigenschaften finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).

### <a name="metadata-overrides"></a>Metadaten-Außerkraftsetzungen
Sie können bestimmte Verhaltensweisen einer Abhängigkeitseigenschaft ändern, indem Sie die Metadaten für diese Eigenschaft überschreiben, wenn Sie von der Klasse ableiten, die die Abhängigkeitseigenschaft ursprünglich registriert. Überschreiben von Metadaten der <xref:System.Windows.DependencyProperty> Bezeichner. Das Überschreiben von Metadaten erfordert keine erneute Implementierung der Eigenschaft. Die Metadatenänderung wird vom Eigenschaftensystem nativ verarbeitet. Jede Klasse kann potenziell individuelle Metadaten für alle Eigenschaften enthalten, die von den Basisklassen jeweils pro Typ geerbt werden.

Im folgende Beispiel überschreibt die Metadaten für eine Abhängigkeitseigenschaft <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>. Das Überschreiben der Metadaten dieser Abhängigkeitseigenschaft ist Teil eines Implementierungsmusters, das Steuerelemente erstellt, die Standardstile aus Designs verwenden können.

[!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
[!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]

Weitere Informationen über das Überschreiben oder Abrufen von Eigenschaftenmetadaten finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).

### <a name="property-value-inheritance"></a>Vererbung von Eigenschaftenwerten
Ein Element kann den Wert einer Abhängigkeitseigenschaft von seinem übergeordneten Element in der Objektstruktur erben.

> [!NOTE]
> Das Vererbungsverhalten von Eigenschaftswerten ist nicht global für alle Abhängigkeitseigenschaften aktiviert, da die Berechnungszeit für die Vererbung Leistungseinbußen mit sich bringt. Die Vererbung von Eigenschaftswerten ist normalerweise nur für Eigenschaften aktiviert, für die die Vererbung von Eigenschaftswerten in einem bestimmten Szenario sinnvoll ist. Anhand des Abschnitts **Informationen zur Abhängigkeitseigenschaft** zu der Abhängigkeitseigenschaft in der SDK-Referenz können Sie ermitteln, ob eine Abhängigkeitseigenschaft erbt.

Das folgende Beispiel zeigt eine Bindung und legt die <xref:System.Windows.FrameworkElement.DataContext%2A> Eigenschaft, die die Quelle der Bindung angibt, die im vorangehenden Beispiel für die Bindung nicht angezeigt wurde. Alle nachfolgenden Bindungen in untergeordneten Objekten nicht auf die Datenquelle angeben müssen, können sie den geerbten Wert aus <xref:System.Windows.FrameworkElement.DataContext%2A> im übergeordneten <xref:System.Windows.Controls.StackPanel> Objekt. (Auch konnte kein untergeordnetes Objekt stattdessen auswählen, direkt über einen eigenen festlegen <xref:System.Windows.FrameworkElement.DataContext%2A> oder ein <xref:System.Windows.Data.Binding.Source%2A> in die <xref:System.Windows.Data.Binding>, und den geerbten Wert absichtlich keine für den Datenkontext der zugehörigen Bindungen verwendet.)

[!code-xaml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]

Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).

### <a name="wpf-designer-integration"></a>WPF-Designer-integration
Ein benutzerdefiniertes Steuerelement mit Eigenschaften, die als Abhängigkeitseigenschaften implementiert werden, erhalten entsprechenden [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]-Support. Ein Beispiel hierfür ist die Fähigkeit, direkte und angefügte Abhängigkeitseigenschaften mit dem **Eigenschaften**-Fenster zu bearbeiten. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).

## <a name="dependency-property-value-precedence"></a>Abhängigkeitseigenschaftswerten
Wenn Sie den Wert einer Abhängigkeitseigenschaft abrufen, erhalten Sie möglicherweise einen Wert, der mithilfe einer der anderen auf Eigenschaften basierenden Eingaben, die Bestandteil des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Systems sind, für die Eigenschaft festgelegt wurde. Abhängigkeitseigenschaftswerten werden Prioritäten zugewiesen, damit eine Vielzahl von Szenarios zur Art und Weise, wie Eigenschaften ihre Werte erhalten, in einer vorhersagbaren Weise interagieren können.

Betrachten Sie das folgende Beispiel. Das Beispiel umfasst ein Format, das gilt für alle Schaltflächen und ihre <xref:System.Windows.Controls.Control.Background%2A> Eigenschaften, sondern klicken Sie dann auch eine Schaltfläche mit einem lokal festgelegten <xref:System.Windows.Controls.Control.Background%2A> Wert.

> [!NOTE]
> In der SDK-Dokumentation werden gelegentlich im Zusammenhang mit Abhängigkeitseigenschaften die Begriffe „lokaler Wert“ oder „lokal festgelegter Wert“ verwendet. Ein lokal festgelegter Wert ist ein Eigenschaftswert, der für eine Objektinstanz direkt im Code oder als Attribut für ein Element in XAML festgelegt wird.  
  
Im Prinzip wird die Eigenschaft für die erste Schaltfläche zweimal festgelegt, wobei nur ein Wert angewendet wird: der Wert mit der höchsten Priorität. Ein lokal festgelegter Wert hat die höchste Priorität (außer einer ausgeführte Animation, aber auf dieses Beispiel ist keine Animation anwendbar), und der lokal festgelegte Wert wird somit anstelle des Werts des Stilsetters für den Hintergrund der ersten Schaltfläche verwendet. Die zweite Schaltfläche weist keinen lokalen Wert auf (ebenso keinen anderen Wert mit höherer Priorität als ein Stilsetter), weswegen der Hintergrund der Schaltfläche dem Stilsetter entstammt.

[!code-xaml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  

### <a name="why-does-dependency-property-precedence-exist"></a>Warum ist die Rangfolge von Abhängigkeit vorhanden?
In der Regel sollen Stile nicht immer gelten und sogar einen lokal festgelegten Wert eines einzelnen Elements verdecken (andernfalls wäre es sehr schwierig, Stile oder Elemente überhaupt zu verwenden). Aus diesem Grund operieren die Werte, die von Stilen abstammen, mit einer niedrigeren Priorität als lokal festgelegte Werte. Eine ausführliche Liste der Abhängigkeitseigenschaften und Angaben dazu, woher der effektive Wert einer Abhängigkeitseigenschaft möglicherweise stammt, finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

> [!NOTE]
> Es gibt eine Reihe von Eigenschaften, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente definiert sind, die keine Abhängigkeitseigenschaften sind. Im Großen und Ganzen wurden Eigenschaften nur als Abhängigkeitseigenschaften implementiert, wenn mindestens eines der Szenarios unterstützt werden musste, das vom Eigenschaftensystem aktiviert wurde: Datenbindungen, Stile, Animationen, die standardmäßige Wertunterstützung, die Vererbung, angefügte Eigenschaften oder Invalidierungen.

## <a name="learning-more-about-dependency-properties"></a>Weitere Informationen zu Abhängigkeitseigenschaften  

- Eine angefügte Eigenschaft ist ein Eigenschaftstyp, die eine spezielle Syntax in XAML unterstützt. Eine angefügte Eigenschaft verfügt oft über keine 1:1-Entsprechung mit einer [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaft und ist nicht unbedingt eine Abhängigkeitseigenschaft. Der Hauptzweck einer angefügten Eigenschaft ist es, den untergeordneten Elementen die Berichterstattung von Eigenschaftswerten an ein übergeordnetes Element zu ermöglichen, selbst wenn diese Eigenschaft in nicht den Klassenmemberlisten des übergeordneten und des untergeordneten Elements vorhanden ist. Eine primäres Szenario ist das Aktivieren von untergeordneten Elementen können Sie das übergeordnete Element zu informieren, wie sie in dargestellt werden soll [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]ist ein Beispiel finden Sie unter <xref:System.Windows.Controls.DockPanel.Dock%2A> oder <xref:System.Windows.Controls.Canvas.Left%2A>. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).

- Komponenten- oder Anwendungsentwickler können ihre eigene Abhängigkeitseigenschaft erstellen, um Funktionen wie die Datenbindung oder die Unterstützung von Stilen oder die Invalidierung und die Erzwingung von Werten zu unterstützen. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).

- Abhängigkeitseigenschaften sollten im Allgemeinen als öffentliches Eigentum gelten, das zugänglich oder zumindest für alle Aufrufer mit Zugriff auf eine Instanz erkennbar sein. Weitere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md).

## <a name="see-also"></a>Siehe auch
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Schreibgeschützte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [WPF-Architektur](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
