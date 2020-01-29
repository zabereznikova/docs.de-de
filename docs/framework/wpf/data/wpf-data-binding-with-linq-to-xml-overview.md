---
title: Datenbindung mit LINQ to XML
ms.date: 10/22/2019
ms.topic: conceptual
ms.openlocfilehash: 3c5567c81d2097a1524f5bbbf9010836ca8c0646
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733819"
---
# <a name="overview-of-wpf-data-binding-with-linq-to-xml"></a>Übersicht über die WPF-Datenbindung mit LINQ to XML

In diesem Artikel werden die Funktionen für die dynamische Datenbindung im <xref:System.Xml.Linq>-Namespace vorgestellt. Diese Features können als Datenquelle für Benutzeroberflächenelemente in WPF-Apps (Windows Presentation Foundation) verwendet werden. Dieses Szenario basiert auf besonderen *dynamischen Eigenschaften* von <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> und <xref:System.Xml.Linq.XElement?displayProperty=fullName>.

## <a name="xaml-and-linq-to-xml"></a>XAML und LINQ to XML

XAML (Extensible Application Markup Language) ist ein von Microsoft eingeführter XML-Dialekt zur Unterstützung von .NET-Technologien. XAML wird in WPF zur Darstellung von Benutzeroberflächenelementen und verwandten Funktionen, wie Ereignissen und Datenbindung, verwendet. In Windows Workflow Foundation wird XAML zur Darstellung der Programmstruktur, z.B. der Programmsteuerung (*Workflows*), verwendet. Mit XAML können deklarative Aspekte einer Technologie vom zugehörigen prozeduralen Code getrennt werden, der eher das individualisierte Verhalten eines Programms definiert.

Für die Interaktion von XAML und LINQ to XML gibt es zwei generelle Möglichkeiten:

- Da XAML-Dateien wohlgeformtes XML sind, können sie mit XML-Technologien, wie LINQ to XML, abgefragt und bearbeitet werden.

- Da LINQ to XML-Abfragen eine Datenquelle darstellen, können diese Abfragen als Datenquelle für die Datenbindung bei WPF-Benutzeroberflächenelementen verwendet werden.

In dieser Dokumentation wird das zweite Szenario beschrieben.

## <a name="data-binding-in-the-windows-presentation-foundation"></a>Datenbindung im Windows Presentation Foundation

Die WPF-Datenbindung ermöglicht es einem Benutzeroberflächenelement, eine seiner Eigenschaften einer Datenquelle zuzuordnen. Ein einfaches Beispiel dafür ist ein <xref:System.Windows.Controls.Label>, dessen Text den Wert einer öffentlichen Eigenschaft in einem benutzerdefinierten Objekt angibt. Die WPF-Datenbindung basiert auf den folgenden Komponenten:

|Komponente|Beschreibung|
|---------------|-----------------|
|Bindungsziel|Das Benutzeroberflächenelement, das der Datenquelle zugeordnet werden soll. Visuelle Elemente in WPF werden von der <xref:System.Windows.UIElement>-Klasse abgeleitet.|
|Zieleigenschaft|Die *Abhängigkeitseigenschaft* des Bindungsziels, das den Wert der Datenbindungsquelle wiedergibt. Abhängigkeitseigenschaften werden direkt von der <xref:System.Windows.DependencyObject>-Klasse unterstützt, von der sich <xref:System.Windows.UIElement> herleitet.|
|Bindungsquelle|Das Quellobjekt für die Werte, die dem Benutzeroberflächenelement für die Präsentation bereitgestellt werden. WPF unterstützt automatisch die folgenden Typen als Bindungsquellen: CLR-Objekte, ADO.NET-Datenobjekte, XML-Daten (aus XPath- oder LINQ to XML-Abfragen) oder ein anderes <xref:System.Windows.DependencyObject>.|
|Quellpfad|Die Eigenschaft der Bindungsquelle, aus der sich der Wert oder der Satz von Werten herleitet, der bzw. die gebunden werden sollen.|

Die Abhängigkeitseigenschaft ist ein WPF-spezifisches Konzept, das eine dynamisch berechnete Eigenschaft eines Benutzeroberflächenelements darstellt. So besitzen Abhängigkeitseigenschaften z. B. häufig Standardwerte oder Werte, die von einem übergeordneten Element bereitgestellt werden. Diese speziellen Eigenschaften werden von Instanzen der <xref:System.Windows.DependencyProperty>-Klasse (und nicht wie bei Standardeigenschaften von Feldern) gestützt. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).

### <a name="dynamic-data-binding-in-wpf"></a>Dynamische Datenbindung in WPF

Standardmäßig erfolgt die Datenbindung nur, wenn das Zielbenutzeroberflächenelement initialisiert wird. Dieser Prozess wird als *einmalige* Bindung bezeichnet. Für die meisten Zwecke reicht dies nicht aus. In der Regel erfordert eine Datenbindungslösung, dass die Änderungen zur Laufzeit mit einer der folgenden Bindungen dynamisch weitergegeben werden:

- *Unidirektionale* Bindung: Diese Form der Bindung bewirkt, dass einseitige Änderungen automatisch weitergegeben werden. In den allermeisten Fällen werden so Änderungen an der Quelle im Ziel wiedergegeben, mitunter ist aber auch der umgekehrte Weg hilfreich.

- *Bidirektionale Bindung*: Änderungen an der Quelle werden automatisch an das Ziel weitergegeben, und Änderungen am Ziel werden automatisch an die Quelle weitergegeben.

Sowohl für die unidirektionale als auch für die bidirektionale Bindung muss die Quelle einen Änderungsbenachrichtigungsmechanismus implementieren. Dies kann z.B. durch die Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle oder durch die Verwendung eines *PropertyNameChanged*-Musters für jede unterstützte Eigenschaft erfolgen.

Weitere Informationen zur Datenbindung in WPF finden Sie unter Übersicht über [Datenbindung (WPF)](/dotnet/framework/wpf/data/data-binding-wpf).

## <a name="dynamic-properties-in-linq-to-xml-classes"></a>Dynamische Eigenschaften in LINQ to XML-Klassen

Die meisten LINQ to XML-Klassen werden nicht als richtige dynamische WPF-Datenquellen angesehen. Einige der nützlichsten Informationen sind nur über Methoden (und nicht über Eigenschaften) verfügbar, und Eigenschaften in diesen Klassen implementieren keine Änderungsbenachrichtigungen. Zur Unterstützung der WPF-Datenbindung macht LINQ to XML einen Satz *dynamischer Eigenschaften* verfügbar.

Diese dynamischen Eigenschaften sind spezielle Laufzeiteigenschaften, die die Funktionalität vorhandener Methoden und Eigenschaften in den Klassen <xref:System.Xml.Linq.XAttribute> und <xref:System.Xml.Linq.XElement> duplizieren. Sie wurden diesen Klassen einzig und allein mit dem Ziel hinzufügt, sie als dynamische Datenquellen für WPF verwenden zu können. Aus diesem Grund implementieren alle diese dynamischen Eigenschaften Änderungsbenachrichtigungen. Eine ausführliche Erläuterung dieser dynamischen Eigenschaften finden Sie im nächsten Abschnitt, [Dynamische Eigenschaften in LINQ to XML](linq-to-xml-dynamic-properties.md).

> [!NOTE]
> Viele der öffentlichen Standardeigenschaften in den verschiedenen Klassen im <xref:System.Xml.Linq>-Namespace können für die einmalige Bindung verwendet werden. Bedenken Sie dabei aber, dass bei diesem Schema weder die Quelle noch das Ziel dynamisch aktualisiert werden.

### <a name="access-dynamic-properties"></a>Zugreifen auf dynamische Eigenschaften

Auf die dynamischen Eigenschaften in den Klassen <xref:System.Xml.Linq.XAttribute> und <xref:System.Xml.Linq.XElement> kann nicht wie auf Standardeigenschaften zugegriffen werden. So gilt z. B. für CLR-kompatible Sprachen wie C# Folgendes:

- Auf die Eigenschaften kann zur Kompilierzeit nicht direkt zugegriffen werden. Dynamische Eigenschaften sind für den Compiler und Visual Studio IntelliSense nicht sichtbar.

- Die Eigenschaften können zur Laufzeit mit .NET-Reflektion weder gefunden noch verwendet werden. Selbst zur Laufzeit handelt es sich bei ihnen nicht um Eigenschaften im eigentlichen CLR-Sinn.

In C# ist der Zugriff auf dynamische Eigenschaften zur Laufzeit nur über die vom <xref:System.ComponentModel>-Namespace bereitgestellten Funktionen möglich.

Im Unterschied dazu kann auf die dynamischen Eigenschaften in einer XML-Quelle über eine unkomplizierte Notation in der folgenden Form zugegriffen werden:

```xml
<object>.<dynamic-property>
```

Die dynamischen Eigenschaften für diese beiden Klassen ergeben entweder einen Wert, der direkt verwendet werden kann, oder einen Indexer, der mit einem Index bereitgestellt werden muss, damit der resultierende Wert oder die resultierende Auflistung von Werten abgerufen werden kann. Für den letzteren Fall gilt folgende Syntax:

```xml
<object>.<dynamic-property>[<index-value>]
```

Weitere Informationen finden Sie unter [Dynamische Eigenschaften in LINQ to XML](linq-to-xml-dynamic-properties.md).

Zur Implementierung der dynamischen WPF-Bindung werden die dynamischen Eigenschaften zusammen mit den vom <xref:System.Windows.Data>-Namespace bereitgestellten Funktionen, insbesondere der <xref:System.Windows.Data.Binding>-Klasse, verwendet.

## <a name="see-also"></a>Siehe auch

- [WPF-Datenbindung mit LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Dynamische Eigenschaften in LINQ to XML](linq-to-xml-dynamic-properties.md)
- [XAML in WPF](../advanced/xaml-in-wpf.md)
- [Datenbindung (WPF)](/dotnet/framework/wpf/data/data-binding-wpf)
- [Verwenden von Workflowmarkup](https://go.microsoft.com/fwlink/?LinkId=98685)
