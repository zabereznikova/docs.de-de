---
title: Übersicht über Abhängigkeitseigenschaften
description: Eine Eigenschaft, die von der WPF-Eigenschaft unterstützt wird, wird als Abhängigkeitseigenschaft bezeichnet. In dieser Übersicht wird das WPF-Eigenschaftensystem und die Funktionen einer Abhängigkeitseigenschaft beschrieben.
ms.date: 06/06/2018
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
ms.openlocfilehash: 542e0a84e4c5cfc3750c33fe29cb40d3643e91e3
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80636031"
---
# <a name="dependency-properties-overview"></a>Übersicht über Abhängigkeitseigenschaften

Windows Presentation Foundation (WPF) bietet eine Reihe von Diensten, die zum Erweitern der Funktionalität einer [Eigenschaft](../../../standard/base-types/common-type-system.md#properties) eines Typs verwendet werden können. Zusammen werden diese Dienste normalerweise als WPF-Eigenschaftensystem bezeichnet. Eine Eigenschaft, die von der WPF-Eigenschaft unterstützt wird, wird als Abhängigkeitseigenschaft bezeichnet. In dieser Übersicht wird das WPF-Eigenschaftensystem und die Funktionen einer Abhängigkeitseigenschaft beschrieben. Dies schließt die Verwendung vorhandener Abhängigkeitseigenschaften in XAML und Code ein. In dieser Übersicht werden auch spezielle Aspekte von Abhängigkeitseigenschaften wie die Metadaten von Abhängigkeitseigenschaften sowie die Erstellung einer eigenen Abhängigkeitseigenschaft in einer benutzerdefinierten Klasse eingeführt.

## <a name="prerequisites"></a>Voraussetzungen
In diesem Thema wird vorausgesetzt, dass Sie über einige grundlegende Kenntnisse zum Typsystem von .NET und die objektorientierte Programmierung verfügen. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem XAML verstehen und wissen, wie WPF-Anwendungen geschrieben werden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="dependency-properties-and-clr-properties"></a>Abhängigkeitseigenschaften und CLR-Eigenschaften
 Eigenschaften werden in der Regel als .NET-[Standardeigenschaften](../../../standard/base-types/common-type-system.md#properties) verfügbar gemacht. Grundsätzlich können Sie direkt mit diesen Eigenschaften direkt interagieren, ohne zu wissen, dass sie als Abhängigkeitseigenschaft implementiert werden. Sie sollten aber mit einigen oder allen Funktionen des WPF-Eigenschaftensystems vertraut sein, damit Sie sie nutzen können.

Abhängigkeitseigenschaften dienen der Berechnung des Werts einer Eigenschaft anhand des Werts von anderen Eingaben. Zu diese anderen Eingaben gehören Systemeigenschaften wie Designs und die Benutzervoreinstellung, Feststellungsmechanismen für Just-In-Time-Eigenschaft wie die Datenbindung und Animationen/Storyboards, mehrfach verwendbare Vorlagen, z.B. Ressourcen und Stile, oder Werte, die über übergeordnete und untergeordnete Beziehungen mit anderen Elementen in der Elementstruktur bekannt sind. Darüber hinaus kann eine Abhängigkeitseigenschaft implementiert werden, um ein selbstständige Überprüfung, Standardwerte, Rückrufe, die Änderungen an anderen Eigenschaften überwachen, sowie ein System bereitzustellen, das Eigenschaftswerte auf Grundlage potenzieller Laufzeitinformationen erzwingen kann. Abgeleitete Klassen können auch einige spezifische Merkmale einer vorhandenen Eigenschaft durch Überschreiben von Metadaten für Abhängigkeitseigenschaften ändern, anstatt die tatsächliche Implementierung der vorhandenen Eigenschaften zu überschreiben oder neue Eigenschaften zu erstellen.

Anhand der SDK-Referenz können Sie ermitteln, welche Eigenschaft eine Abhängigkeitseigenschaft ist, wenn diese im Abschnitt „Informationen zur Abhängigkeitseigenschaft“ auf der verwalteten Referenzseite für diese Eigenschaft vorhanden ist. Der Abschnitt mit den Informationen zur Abhängigkeitseigenschaft enthält einen Link zum <xref:System.Windows.DependencyProperty>-Bezeichner für diese Abhängigkeitseigenschaft und eine Liste der Metadatenoptionen für diese Eigenschaft, der Informationen für das Überschreiben pro Klasse und anderer Details.

## <a name="dependency-properties-back-clr-properties"></a>Abhängigkeitseigenschaften unterstützen CLR-Eigenschaften
Abhängigkeitseigenschaften und das WPF-Eigenschaftensystem erweitern die Funktionalität von Eigenschaften durch die Bereitstellung eines Typs, der eine Eigenschaft als eine alternative Implementierung zum Standardmuster unterstützt, bei dem die Eigenschaft mit einem privaten Feld unterstützt wird. Der Name dieses Typs lautet <xref:System.Windows.DependencyProperty>. Der andere wichtige Typ, der das WPF-Eigenschaftensystem definiert, ist <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject> definiert die Basisklasse, die eine Abhängigkeitseigenschaft registrieren und besitzen kann.

Nachfolgend ist die Terminologie aufgeführt, die mit Abhängigkeitseigenschaften verwendet wird:

- **Abhängigkeitseigenschaft:** Eine Eigenschaft, die von einer <xref:System.Windows.DependencyProperty>-Klasse gesichert wird.

- **Abhängigkeitseigenschaftenbezeichner:** Eine <xref:System.Windows.DependencyProperty>-Instanz, die als Rückgabewert beim Registrieren einer Abhängigkeitseigenschaft abgerufen und dann als statischer Member einer Klasse gespeichert wird. Dieser Bezeichner wird als Parameter für viele der APIs verwendet, die mit dem WPF-Eigenschaftenssystem interagieren.

- **CLR-Wrapper:** Die tatsächlichen Implementierungen zum Abrufen und Festlegen für die Eigenschaft. Diese Implementierungen beinhalten den Abhängigkeitseigenschaftenbezeichner, indem sie diesen in den Aufrufen <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> verwenden und so die Sicherung für die Eigenschaft über das WPF-Eigenschaftensystem bereitstellen.

Das folgende Beispiel definiert die `IsSpinning`-Abhängigkeitseigenschaft und zeigt die Beziehung zwischen dem <xref:System.Windows.DependencyProperty>-Bezeichner zur Eigenschaft, die er unterstützt.

[!code-csharp[PropertiesOvwSupport#DPFormBasic](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
[!code-vb[PropertiesOvwSupport#DPFormBasic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
  
Die Namenskonvention der Eigenschaft und ihres unterstützenden <xref:System.Windows.DependencyProperty>-Feld ist wichtig. Der Name des Felds ist immer der Name der Eigenschaft, die mit dem Suffix `Property` endet. Weitere Informationen zu dieser Konvention und die Gründe dafür finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).  

## <a name="setting-property-values"></a>Festlegen von Eigenschaftswerten
Sie können Eigenschaften sowohl im Code als auch in XAML festlegen.

### <a name="setting-property-values-in-xaml"></a>Festlegen von Eigenschaftswerten in XAML
Im folgende XAML-Beispiel wird die Hintergrundfarbe einer Schaltfläche als Rot dargestellt. Dieses Beispiel zeigt einen Fall, in dem der einfache Zeichenfolgenwert für ein XAML-Attribut vom WPF XAML-Parser im generierten Code in einen WPF-Typ typkonvertiert wird (ein <xref:System.Windows.Media.Color> mit einer <xref:System.Windows.Media.SolidColorBrush>).

[!code-xaml[PropertiesOvwSupport#MostBasicProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]

XAML unterstützt eine Vielzahl an Syntaxformen zum Festlegen von Eigenschaften. Welche Syntax für eine bestimmte Eigenschaft verwendet wird, hängt vom Werttyp ab, den eine Eigenschaft verwendet, sowie von anderen Faktoren wie dem Vorhandensein eines Typkonverters. Weitere Informationen zur XAML-Syntax zum Festlegen von Eigenschaften finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) und [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md).

Im folgende XAML-Beispiel wird ein Beispiel für eine Syntax ohne Attribut und einen anderen Hintergrund für eine Schaltfläche. Diesmal wird nicht einfach eine Volltonfarbe, sondern der Hintergrund auf ein Bild mit einem Element festgelegt, das dieses Bild und die Bildquelle angegeben als Attribut des geschachtelten Elements darstellt. Dies ist ein Beispiel für Eigenschaftenelementsyntax.

[!code-xaml[PropertiesOvwSupport#PESyntaxProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]

### <a name="setting-properties-in-code"></a>Festlegen von Eigenschaften im Code
 Das Festlegen von Abhängigkeitseigenschaftswerten im Code ist in der Regel nur ein Aufruf der Setimplementierung, die vom CLR-"Wrapper" verfügbar gemacht wird.

[!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
[!code-vb[PropertiesOvwSupport#ProceduralPropertySet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]

Das Abrufen eines Eigenschaftswerts besteht auch im Grunde aus einem Aufruf der Implementierung zum Abrufen des Wrappers:

[!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]

Sie können auch die Eigenschaftensystem-APIs <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> und direkt aufrufen. Dies ist in der Regel nicht erforderlich, wenn Sie vorhandene Eigenschaften verwenden (die Wrapper sind bequemer und bieten eine bessere Belichtung der Eigenschaft für Entwicklertools), aber das direkte Aufrufen der APIs ist für bestimmte Szenarien geeignet.

Eigenschaften können auch in XAML festgelegt und später über den Code (über die CodeBehind-Datei) darauf zugegriffen werden. Weitere Informationen finden Sie unter [Code-Behind und XAML in WPF](code-behind-and-xaml-in-wpf.md).

## <a name="property-functionality-provided-by-a-dependency-property"></a>Von einer Abhängigkeitseigenschaft bereitgestellte Eigenschaftenfunktionalität
Eine Abhängigkeitseigenschaft stellt Funktionen bereit, die die Funktionalität einer Eigenschaft gegenüber einer Eigenschaft übertreffen, die durch ein Feld unterstützt wird. Oft stellt eine solche Funktion eine der folgenden spezifischen Features dar bzw. unterstützt es:

- [Ressourcen](#resources)

- [Datenbindung](#data-binding)

- [Stile](#styles)

- [Animationen](#animations)

- [Überschreiben von Metadaten](#metadata-overrides)

- [Vererbung von Eigenschaftswerten](#property-value-inheritance)

- [WPF-Designer-Integration](#wpf-designer-integration)

### <a name="resources"></a>Ressourcen
Ein Wert einer Abhängigkeitseigenschaft kann durch Verweisen auf eine Ressource festgelegt werden. Ressourcen werden in der Regel als der `Resources`-Eigenschaftswert eines Seitenstammelements oder der Anwendung angegeben (diese Positionen ermöglichen den einfachsten Zugriff auf die Ressource). Das folgende Beispiel veranschaulicht, wie Sie eine <xref:System.Windows.Media.SolidColorBrush>-Ressource definieren.

[!code-xaml[PropertiesOvwSupport#ResourcesResource](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]

Nachdem die Ressource definiert wurde, können Sie auf die Ressource verweisen und einen Eigenschaftswert bereitstellen:

[!code-xaml[PropertiesOvwSupport#ResourcesReference](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]

Auf diese spezielle Ressource wird als ein [DynamicResource-Markuperweiterung](dynamicresource-markup-extension.md) verwiesen (in WPF-XAML können Sie entweder einen statischen oder dynamischen Ressourcenverweis verwenden). Um einen dynamischen Ressourcenverweis zu verwenden, müssen Sie die Ressource auf eine Abhängigkeitseigenschaft festlegen. Daher wird vom WPF-Eigenschaftensystem insbesondere die Verwendung dynamischer Ressourcenverweise ermöglicht. Weitere Informationen finden Sie unter [XAML-Ressourcen](xaml-resources.md).

> [!NOTE]
> Ressourcen werden als ein lokaler Wert behandelt. Wenn Sie also einen anderen lokalen Wert festgelegt haben, beseitigen Sie den Verweis auf die Ressource. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).

### <a name="data-binding"></a>Datenbindung
Eine Abhängigkeitseigenschaft kann über die Datenbindung auf einen Wert verweisen. Die Datenbindung funktioniert über eine bestimmte Markuperweiterungssyntax in XAML oder das <xref:System.Windows.Data.Binding>-Objekt im Code. Mit der Datenbindung wird die letzte Bestimmung des Eigenschaftswerts bis zur Laufzeit zurückgestellt. Zu diesem Zeitpunkt wird der Wert aus einer Datenquelle abgerufen.

Das folgende Beispiel legt mithilfe einer in XAML deklarierten Bindung die Eigenschaft <xref:System.Windows.Controls.ContentControl.Content%2A> für eine <xref:System.Windows.Controls.Button>-Klasse fest. Die Bindung verwendet einen geerbten Datenkontext sowie eine <xref:System.Windows.Data.XmlDataProvider>-Datenquelle (hier nicht gezeigt). Die Bindung selbst gibt die gewünschte Quelleigenschaft mithilfe von <xref:System.Windows.Data.Binding.XPath%2A> innerhalb der Datenquelle an.

[!code-xaml[PropertiesOvwSupport#BasicInlineBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]

> [!NOTE]
> Bindungen werden als ein lokaler Wert behandelt. Wenn Sie also einen anderen lokalen Wert festgelegt haben, beseitigen Sie die Bindung. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).

Die Abhängigkeitseigenschaften (oder die <xref:System.Windows.DependencyObject>-Klasse) unterstützen <xref:System.ComponentModel.INotifyPropertyChanged> nicht nativ zu Zwecken der Erstellung von Benachrichtigungen von Änderungen im Wert <xref:System.Windows.DependencyObject> für die Quelleigenschaft für Datenbindungsvorgänge. Weitere Informationen zum Erstellen von Eigenschaften für die Datenbindung, die Änderungen an einem Datenbindungsziel melden können, finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).

### <a name="styles"></a>Stile
Stile und Vorlagen sind zwei Hauptgründe für die Verwendung von Abhängigkeitseigenschaften. Stile eignen sich besonders für das Festlegen von Eigenschaften, die die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Anwendung definieren. Stile werden in XAML in der Regel als Ressourcen definiert. Stile interagieren mit dem Eigenschaftensystem, weil sie normalerweise sowohl „Setter“ für bestimmte Eigenschaften als auch „Trigger“ enthalten, die einen Eigenschaftswert basierend auf dem Echtzeitwert einer anderen Eigenschaft ändern.

Im folgenden Beispiel wird ein einfacher Stil <xref:System.Windows.FrameworkElement.Resources%2A> erstellt (der in einem Wörterbuch definiert <xref:System.Windows.FrameworkElement.Style%2A> und <xref:System.Windows.Controls.Button>nicht angezeigt wird), und wendet diesen Stil dann direkt auf die Eigenschaft für eine an. Der Setter innerhalb des Stils legt die Eigenschaft <xref:System.Windows.Controls.Control.Background%2A> für eine formatierte <xref:System.Windows.Controls.Button> auf „green“ (grün) fest.

[!code-xaml[PropertiesOvwSupport#SimpleStyleDef](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]

[!code-xaml[PropertiesOvwSupport#SimpleStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]

Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).

### <a name="animations"></a>Animations
Abhängigkeitseigenschaften können animiert werden. Wenn eine Animation angewendet wurde und ausgeführt wird, verfügt der animierte Wert über eine höhere Priorität als alle anderen Werte (z.B. ein lokaler Wert), über die die Eigenschaft sonst verfügt.

Im folgenden Beispiel wird die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf einer <xref:System.Windows.Controls.Button>-Eigenschaft animiert (genau genommen wird <xref:System.Windows.Controls.Control.Background%2A> über die Eigenschaftenelementsyntax animiert, um eine leere <xref:System.Windows.Media.SolidColorBrush>-Klasse als <xref:System.Windows.Controls.Control.Background%2A> anzugeben. Die <xref:System.Windows.Media.SolidColorBrush.Color%2A>-Eigenschaft dieser <xref:System.Windows.Media.SolidColorBrush> ist somit die Eigenschaft, die direkt animiert wird).

[!code-xaml[PropertiesOvwSupport#MiniAnimate](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]

Weitere Informationen zur Animation von Eigenschaften finden Sie unter [Übersicht über Animationen](../graphics-multimedia/animation-overview.md) und [Übersicht über Storyboards](../graphics-multimedia/storyboards-overview.md).

### <a name="metadata-overrides"></a>Überschreiben von Metadaten
Sie können bestimmte Verhaltensweisen einer Abhängigkeitseigenschaft ändern, indem Sie die Metadaten für diese Eigenschaft überschreiben, wenn Sie von der Klasse ableiten, die die Abhängigkeitseigenschaft ursprünglich registriert. Das Überschreiben von Metadaten basiert auf dem Bezeichner <xref:System.Windows.DependencyProperty>. Das Überschreiben von Metadaten erfordert keine erneute Implementierung der Eigenschaft. Die Metadatenänderung wird vom Eigenschaftensystem nativ verarbeitet. Jede Klasse kann potenziell individuelle Metadaten für alle Eigenschaften enthalten, die von den Basisklassen jeweils pro Typ geerbt werden.

Das folgende Beispiel überschreibt Metadaten für eine <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>-Abhängigkeitseigenschaft. Das Überschreiben der Metadaten dieser Abhängigkeitseigenschaft ist Teil eines Implementierungsmusters, das Steuerelemente erstellt, die Standardstile aus Designs verwenden können.

[!code-csharp[PropertiesOvwSupport#OverrideMetadata](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
[!code-vb[PropertiesOvwSupport#OverrideMetadata](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]

Weitere Informationen über das Überschreiben oder Abrufen von Eigenschaftenmetadaten finden Sie unter [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).

### <a name="property-value-inheritance"></a>Vererbung von Eigenschaftswerten
Ein Element kann den Wert einer Abhängigkeitseigenschaft von seinem übergeordneten Element in der Objektstruktur erben.

> [!NOTE]
> Das Vererbungsverhalten von Eigenschaftswerten ist nicht global für alle Abhängigkeitseigenschaften aktiviert, da die Berechnungszeit für die Vererbung Leistungseinbußen mit sich bringt. Die Vererbung von Eigenschaftswerten ist normalerweise nur für Eigenschaften aktiviert, für die die Vererbung von Eigenschaftswerten in einem bestimmten Szenario sinnvoll ist. Anhand des Abschnitts **Informationen zur Abhängigkeitseigenschaft** zu der Abhängigkeitseigenschaft in der SDK-Referenz können Sie ermitteln, ob eine Abhängigkeitseigenschaft erbt.

Im folgenden Beispiel wird eine Bindung gezeigt und die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft festgelegt, die die Quelle der Bindung angibt, die im früheren Bindungsbeispiel nicht gezeigt wurde. Alle nachfolgenden Bindungen in untergeordneten Objekt müssen die Quelle nicht angeben. Sie können den geerbten Wert von <xref:System.Windows.FrameworkElement.DataContext%2A> im übergeordneten <xref:System.Windows.Controls.StackPanel>-Objekt verwenden. (Alternativ kann ein untergeordnetes Objekt stattdessen direkt seine eigene <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft oder eine <xref:System.Windows.Data.Binding.Source%2A> in der <xref:System.Windows.Data.Binding> angeben und so bewusst den geerbten Wert für den Datenkontext der Bindungen nicht verwenden.)

[!code-xaml[PropertiesOvwSupport#InheritanceContext](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]

Weitere Informationen finden Sie unter [Vererbung von Eigenschaftswerten](property-value-inheritance.md).

### <a name="wpf-designer-integration"></a>WPF-Designer-Integration
Ein benutzerdefiniertes Steuerelement mit Eigenschaften, die als Abhängigkeitseigenschaften implementiert sind, wird von WPF Designer für Visual Studio unterstützt. Ein Beispiel hierfür ist die Fähigkeit, direkte und angefügte Abhängigkeitseigenschaften mit dem **Eigenschaften**-Fenster zu bearbeiten. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).

## <a name="dependency-property-value-precedence"></a>Priorität von Abhängigkeitseigenschaftswerten
Wenn Sie den Wert einer Abhängigkeitseigenschaft abrufen, erhalten Sie möglicherweise einen Wert, der mithilfe einer der anderen auf Eigenschaften basierenden Eingaben, die Bestandteil des WPF-Systems sind, für die Eigenschaft festgelegt wurde. Abhängigkeitseigenschaftswerten werden Prioritäten zugewiesen, damit eine Vielzahl von Szenarios zur Art und Weise, wie Eigenschaften ihre Werte erhalten, in einer vorhersagbaren Weise interagieren können.

Betrachten Sie das folgende Beispiel. Das Beispiel enthält einen Stil, der für alle Schaltflächen und deren <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaften gilt, aber ebenso eine Schaltfläche mit einem lokal festgelegten <xref:System.Windows.Controls.Control.Background%2A>-Wert angibt.

> [!NOTE]
> In der SDK-Dokumentation werden gelegentlich im Zusammenhang mit Abhängigkeitseigenschaften die Begriffe „lokaler Wert“ oder „lokal festgelegter Wert“ verwendet. Ein lokal festgelegter Wert ist ein Eigenschaftswert, der für eine Objektinstanz direkt im Code oder als Attribut für ein Element in XAML festgelegt wird.  
  
Im Prinzip wird die Eigenschaft für die erste Schaltfläche zweimal festgelegt, wobei nur ein Wert angewendet wird: der Wert mit der höchsten Priorität. Ein lokal festgelegter Wert hat die höchste Priorität (außer einer ausgeführte Animation, aber auf dieses Beispiel ist keine Animation anwendbar), und der lokal festgelegte Wert wird somit anstelle des Werts des Stilsetters für den Hintergrund der ersten Schaltfläche verwendet. Die zweite Schaltfläche weist keinen lokalen Wert auf (ebenso keinen anderen Wert mit höherer Priorität als ein Stilsetter), weswegen der Hintergrund der Schaltfläche dem Stilsetter entstammt.

[!code-xaml[PropertiesOvwSupport#MiniPrecedence](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  

### <a name="why-does-dependency-property-precedence-exist"></a>Warum haben Abhängigkeitseigenschaften Prioritäten?
In der Regel möchten Sie nicht, dass Stile immer angewendet werden und sogar einen lokal festgelegten Wert eines einzelnen Elements verdecken (andernfalls wäre es schwierig, Stile oder Elemente im Allgemeinen zu verwenden). Aus diesem Grund operieren die Werte, die von Stilen abstammen, mit einer niedrigeren Priorität als lokal festgelegte Werte. Eine ausführliche Liste der Abhängigkeitseigenschaften und Angaben dazu, woher der effektive Wert einer Abhängigkeitseigenschaft möglicherweise stammt, finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).

> [!NOTE]
> Es gibt eine Reihe von Eigenschaften, die für WPF-Elemente definiert sind, die keine Abhängigkeitseigenschaften sind. Im Großen und Ganzen wurden Eigenschaften nur als Abhängigkeitseigenschaften implementiert, wenn mindestens eines der Szenarios unterstützt werden musste, das vom Eigenschaftensystem aktiviert wurde: Datenbindungen, Stile, Animationen, die standardmäßige Wertunterstützung, die Vererbung, angefügte Eigenschaften oder Invalidierungen.

## <a name="learning-more-about-dependency-properties"></a>Wissenswertes zu Abhängigkeitseigenschaften  

- Eine angefügte Eigenschaft ist ein Eigenschaftstyp, die eine spezielle Syntax in XAML unterstützt. Eine angefügte Eigenschaft verfügt häufig nicht über eine 1:1-Entsprechung mit einer CLR-Eigenschaft (Common Language Runtime) und ist nicht notwendigerweise eine Abhängigkeitseigenschaft. Der typische Zweck einer angefügten Eigenschaft besteht darin, untergeordneten Elementen das Melden von Eigenschaftswerten an ein übergeordnetes Element zu ermöglichen, auch wenn das übergeordnete Element und das untergeordnete Element nicht beide diese Eigenschaft als Teil der Auflistungen von Klassenmembern besitzen. Ein primäres Szenario ist das Aktivieren von untergeordneten Elementen, um das übergeordnete Element darüber zu informieren, wie die untergeordneten Elemente in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dargestellt werden sollen. Ein Beispiel finden Sie unter <xref:System.Windows.Controls.DockPanel.Dock%2A> oder <xref:System.Windows.Controls.Canvas.Left%2A>. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](attached-properties-overview.md).

- Komponenten- oder Anwendungsentwickler können ihre eigene Abhängigkeitseigenschaft erstellen, um Funktionen wie die Datenbindung oder die Unterstützung von Stilen oder die Invalidierung und die Erzwingung von Werten zu unterstützen. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md).

- Betrachten Sie Abhängigkeitseigenschaften als öffentliche Eigenschaften, auf die zugegriffen werden kann oder zumindest von jedem Aufrufer erkannt werden kann, der Zugriff auf eine Instanz hat. Weitere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md).

## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Schreibgeschützte Abhängigkeitseigenschaften](read-only-dependency-properties.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [WPF-Architektur](wpf-architecture.md)
