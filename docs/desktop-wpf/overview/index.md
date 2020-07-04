---
title: Was ist Windows Presentation Foundation?
description: Dieser Artikel bietet eine Übersicht darüber, was Windows Presentation Foundation (WPF) bezogen auf .NET Core ist und welche Funktionen bereitgestellt werden.
ms.date: 07/18/2019
ms.topic: overview
ms.openlocfilehash: 63b2e431b5ab5fd3875887b8b574a77aa12018a6
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "85840278"
---
# <a name="what-is-windows-presentation-foundation"></a>Was ist Windows Presentation Foundation?

Willkommen beim Desktopleitfaden zu Windows Presentation Foundation (WPF), einem Benutzeroberflächenframework, mit dem Desktopclientanwendungen für Windows erstellt werden können. Die WPF-Entwicklungsplattform unterstützt eine breite Palette an Anwendungsentwicklungsfeatures, darunter ein Anwendungsmodell, Steuerelemente, Grafik und Datenbindung. WPF verwendet XAML (Extensible Application Markup Language), um ein deklaratives Modell für die Anwendungsprogrammierung bereitzustellen.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Es gibt zwei Implementierungen von WPF:

01. Die Open-Source-Implementierung, die auf [GitHub](https://github.com/dotnet/wpf) gehostet wird. Diese Version wird unter .NET Core 3.0 ausgeführt. Der visuelle WPF-Designer für XAML erfordert mindestens [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide).

01. Die .NET Framework-Implementierung, die von Visual Studio 2019 und Visual Studio 2017 unterstützt wird.

Dieser Desktopleitfaden bezieht sich auf .NET Core 3.0 und WPF. Weitere Informationen zur vorhandenen Dokumentation für WPF mit .NET Framework finden Sie unter [Framework „Windows Presentation Foundation“](../../framework/wpf/index.md).

## <a name="xaml"></a>XAML

Bei XAML handelt es sich um eine deklarative XML-basierte Sprache, die von WPF beispielsweise zum Definieren von Ressourcen oder Benutzeroberflächenelementen verwendet wird. Elemente, die in XAML definiert werden, stellen die Instanziierung von Objekten aus einer Assembly dar. XAML unterscheidet sich von den meisten anderen Markupsprachen, die zur Laufzeit interpretiert werden, ohne dass eine direkte Bindung an ein unterstützendes Typsystem besteht.

Das folgende Beispiel zeigt, wie Sie eine Schaltfläche als Teil einer Benutzeroberfläche erstellen können. Dieses Beispiel soll Ihnen zeigen, wie XAML ein Objekt darstellt, wobei `Button` der Typ und `Content` eine Eigenschaft ist.

```xaml
<StackPanel>
    <Button Content="Click Me!" />
</StackPanel>
```

<!--For more information, see [XAML overview (WPF)](../../../framework/wpf/advanced/xaml-overview-wpf.md).-->

### <a name="xaml-extensions"></a>XAML-Erweiterungen

XAML stellt Syntax für Markuperweiterungen bereit. Markuperweiterungen können verwendet werden, um Werte für Eigenschaften in Attributform, Eigenschaft-Element-Form oder in beiden Formen bereitzustellen.

Der XAML-Code oben hat z. B. eine Schaltfläche definiert, bei der der sichtbare Inhalt auf die Literalzeichenfolge `"Click Me!"` festgelegt wird, aber der Inhalt kann stattdessen von einer unterstützten Markuperweiterung festgelegt werden. Eine Markuperweiterung wird mit öffnenden und schließenden geschweiften Klammern (`{ }`) definiert. Das Zeichenfolgentoken, das unmittelbar auf die öffnende geschweifte Klammer folgt, bestimmt den Typ der Markuperweiterung.

```xaml
<StackPanel>
    <Button Content="{MarkupType}" />
</StackPanel>
```

WPF bietet verschiedene Markuperweiterungen für XAML, z. B. `{Binding}` für Datenbindung.

Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="property-system"></a>Eigenschaftensystem

WPF bietet eine Reihe von Diensten, die zum Erweitern der Funktionalität einer [Eigenschaft](../../standard/base-types/common-type-system.md#properties) eines Typs verwendet werden können. Zusammen werden diese Dienste als *WPF-Eigenschaftensystem* bezeichnet. Eine Eigenschaft, die von der WPF-Eigenschaft unterstützt wird, wird als Abhängigkeitseigenschaft bezeichnet.

Abhängigkeitseigenschaften erweitern die Eigenschaftsfunktionalität durch Bereitstellen des <xref:System.Windows.DependencyProperty>-Typs, der eine Eigenschaft unterstützt. Der Typ der Abhängigkeitseigenschaft ist eine alternative Implementierung des Standardmusters, bei dem die Eigenschaft durch ein privates Feld unterstützt wird.

### <a name="dependency-property"></a>Abhängigkeitseigenschaft

In WPF werden Abhängigkeitseigenschaften in der Regel als .NET-[Standardeigenschaften](../../standard/base-types/common-type-system.md#properties) bereitgestellt. Grundsätzlich können Sie direkt mit diesen Eigenschaften direkt interagieren, ohne zu wissen, dass sie als Abhängigkeitseigenschaft implementiert werden.

Abhängigkeitseigenschaften dienen der Berechnung des Werts einer Eigenschaft anhand des Werts von anderen Eingaben. Diese anderen Eingaben können Systemeigenschaften (z. B. Designs und Benutzereinstellungen) oder eine Just-in-Time-Eigenschaft aus der Datenbindung und Animationen umfassen.

Eine Abhängigkeitseigenschaft kann implementiert werden, um Validierung, Standardwerte und Rückrufe bereitzustellen, die Änderungen an anderen Eigenschaften überwachen. Abgeleitete Klassen können auch einige spezifische Eigenschaften einer vorhandenen Eigenschaft ändern, indem sie die Metadaten der Abhängigkeitseigenschaften überschreiben, anstatt eine neue Eigenschaft zu erstellen oder eine vorhandene Eigenschaft zu überschreiben.

### <a name="dependency-object"></a>Abhängigkeitsobjekt

Ein anderer Typ, der wichtig für das WPF-Eigenschaftensystem ist, ist <xref:System.Windows.DependencyObject>. Dieser Typ definiert die Basisklasse, die eine Abhängigkeitseigenschaft registrieren und besitzen kann. Die Methoden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> stellen die unterstützende Implementierung der Abhängigkeitseigenschaft für die Abhängigkeitsobjektinstanz bereit.

Das folgende Beispiel zeigt ein Abhängigkeitsobjekt, das einen einzelnen Abhängigkeitseigenschaftbezeichner namens `ValueProperty` definiert. Die Abhängigkeitseigenschaft wird mit der .NET-Eigenschaft `Value` erstellt.

```csharp
public class TextField: DependencyObject
{
    public static readonly DependencyProperty ValueProperty =
        DependencyProperty.Register("Value", typeof(string), typeof(TextField), new PropertyMetadata(""));

    public string Value
    {
        get { return (string)GetValue(ValueProperty); }
        set { SetValue(ValueProperty, value); }
    }
}
```

Die Abhängigkeitseigenschaft wird als statischer Member eines Abhängigkeitsobjekttyps definiert, z. B. mit `TextField` im Beispiel oben. Die Abhängigkeitseigenschaft muss beim Abhängigkeitsobjekt registriert werden.

Die `Value`-Eigenschaft im Beispiel oben umschließt die Abhängigkeitseigenschaft und stellt das .NET-Eigenschaftenstandardmuster bereit, das Sie wahrscheinlich kennen.

<!--For more information, see [Dependency properties overview](../../../framework/wpf/advanced/dependency-properties-overview.md).-->

## <a name="events"></a>Ereignisse

WPF bietet ein Ereignissystem, das auf den .NET CLR-Ereignissen (Common Language Runtime) aufsetzt, mit denen Sie vertraut sind. Diese WPF-Ereignisse werden als Routingereignisse bezeichnet.

Ein Routingereignis ist ein CLR-Ereignis, das von einer Instanz der `RoutedEvent`-Klasse unterstützt und im WPF-Ereignissystem registriert wird. Die aus der Ereignisregistrierung abgerufene `RoutedEvent`-Instanz bleibt in der Regel als ein `public static readonly`-Feldmember der Klasse erhalten, die das Routingereignis registriert und somit dessen *Besitzer* ist. Die Verbindung mit dem identisch benannten CLR-Ereignis (das manchmal auch als *Wrapper*-Ereignis bezeichnet wird) erfolgt durch das Außerkraftsetzen der `add`- und `remove`-Implementierungen für das CLR-Ereignis. Der Unterstützungs- und Verbindungsmechanismus des Routingereignisses ist vom Konzept her genauso wie eine [Abhängigkeitseigenschaft](#dependency-property) eine CLR-Eigenschaft ist, die von der `DependencyProperty`-Klasse unterstützt und im WPF-Eigenschaftensystem registriert wird.

Der Hauptvorteil des Routingereignissystems besteht darin, dass Ereignisse in der Steuerelementstruktur *aufsteigen*, um nach einem Handler zu suchten. Da WPF z. B. ein umfangreiches Inhaltsmodell aufweist, legen Sie ein Bildsteuerelement als Inhalt eines Schaltflächensteuerelements fest. Wenn mit der Maus auf das Bildsteuerelement geklickt wird, würden Sie erwarten, dass es die Mausereignisse verarbeitet und somit die Treffertests unterbricht, die dazu führen, dass eine Schaltfläche das `Click`-Ereignis aufruft. In einem herkömmlichen CLR-Ereignismodell würden Sie diese Einschränkung umgehen, indem Sie denselben Handler an das Bild und die Schaltfläche anfügen. Mit dem Routingereignissystem steigen die Mausereignisse, die für das Bildsteuerelement aufgerufen werden (z. B. seine Auswahl), jedoch zum übergeordneten Schaltflächensteuerelement auf.

<!--For more information, including other types of event models, see [Events overview](../../../framework/wpf/advanced/routed-events-overview.md).-->

## <a name="data-binding"></a>Datenbindung

WPF-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können an Daten aus unterschiedlichen Typen von Datenquellen in Form von CLR-Objekten (Common Language Runtime) und XML gebunden werden. WPF bietet außerdem einen Mechanismus für die Übertragung von Daten durch Drag & Drop-Vorgänge.

Datenbindung ist der Vorgang, bei dem eine Verbindung zwischen der Benutzeroberfläche der Anwendung und der Geschäftslogik eingerichtet wird. Wenn die Bindung ordnungsgemäße Einstellungen aufweist und die Daten die richtigen Benachrichtigungen bereitstellen, ändern sich die an die Daten gebundenen Elemente automatisch bei jeder Änderung des Werts der Daten, sodass die Änderungen entsprechend wiedergespiegelt werden. Datenbindung kann auch bedeuten, dass bei einer Änderung der äußeren Darstellung von Daten in einem Element die zugrunde liegenden Daten automatisch aktualisiert werden, um die Änderung widerzuspiegeln. Wenn der Benutzer beispielsweise den Wert in einem TextBox-Element bearbeitet, wird der zugrunde liegende Datenwert automatisch aktualisiert, um diese Änderung widerzuspiegeln.

Datenbindung kann in XAML über die `{Binding}`-Markuperweiterung konfiguriert werden. Im folgenden Beispiel wird die Bindung an die `ButtonText`-Eigenschaft eines Datenobjekts veranschaulicht. Wenn diese Bindung fehlschlägt, wird der Wert `Click Me!` verwendet.

```xaml
<StackPanel>
    <Button Content="{Binding ButtonText, FallbackValue='Click Me!'}" />
</StackPanel>
```

Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../data/data-binding-overview.md).

## <a name="ui-components"></a>Benutzeroberflächenkomponenten

WPF stellt viele der gängigen Komponenten der Benutzeroberfläche zur Verfügung, die in nahezu jeder Windows-Anwendung zum Einsatz kommen, beispielsweise `Button`, `Label`, `TextBox`, `Menu` und `ListBox`. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Während im WPF-SDK weiterhin der Begriff „Steuerelement“ (Control) für jede Klasse verwendet wird, die ein sichtbares Objekt in einer Anwendung darstellt, ist es wichtig zu beachten, dass eine Klasse nicht notwendigerweise von der `Control`-Klasse erben muss, um eine sichtbare Präsenz zu haben. Klassen, die von der `Control`-Klasse erben, enthalten ein `ControlTemplate`-Objekt, das es dem Benutzer eines Steuerelements ermöglicht, die Darstellung des Steuerelements radikal zu ändern, ohne eine neue Unterklasse erstellen zu müssen.

## <a name="styles-and-templates"></a>Stile und Vorlagen

Zum Erstellen von Stilen und Vorlagen in WPF stehen eine Reihe von Funktionen (Stile, Vorlagen, Trigger und Storyboards) zur Verfügung, die es einer Anwendung, einem Dokument oder dem Entwickler einer Benutzeroberfläche ermöglichen, visuell ansprechende Effekte zu erstellen und ein einheitliches Erscheinungsbild des Produkts zu erzielen.

Ein weiteres Feature des WPF-Stilmodells ist die Trennung von Präsentation und Logik, d. h. Designer können an der Darstellung einer Anwendung mit XAML arbeiten, während Entwickler an anderer Stelle an der Programmierlogik arbeiten.

Darüber hinaus ist es wichtig, die Ressourcen zu kennen, die die Wiederverwendung von Stilen und Vorlagen ermöglichen.

Weitere Informationen finden Sie unter [Stile und Vorlagen](../fundamentals/styles-templates-overview.md).

## <a name="resources"></a>Ressourcen

WPF-Ressourcen sind Objekte, die an unterschiedlichen Stellen in der Anwendung erneut verwendet werden können. Beispiele für Ressourcen sind Stile, Vorlagen und Farbpinsel. Ressourcen können sowohl im Code als auch im XAML-Format definiert und referenziert werden.

Jedes Element auf Frameworkebene (<xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>) verfügt über eine `Resources`-Eigenschaft. Hierbei handelt es sich um einen <xref:System.Windows.ResourceDictionary>-Typ, der definierte Ressourcen enthält. Da alle-Elemente von einem Element auf Frameworkebene erben, können alle Elemente Ressourcen definieren. Meistens werden Ressourcen jedoch für ein Stammelement eines XAML-Dokuments definiert.

<!--For more information, see [XAML Resources](../../../framework/wpf/advanced/xaml-resources.md).-->

## <a name="next-steps"></a>Nächste Schritte

- [Erstellen einer WPF-Anwendung.](https://docs.microsoft.com/visualstudio/get-started/csharp/tutorial-wpf?toc=/dotnet/desktop-wpf/toc.json&bc=/dotnet/breadcrumb/toc.json)
- [Untersuchen der Unterschiede zu .NET Framework.](../migration/differences-from-net-framework.md)
- [Weitere Informationen zu XAML.](../fundamentals/xaml.md)
