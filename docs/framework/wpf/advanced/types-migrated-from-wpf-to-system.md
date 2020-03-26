---
title: Aus WPF zu System.Xaml migrierte Typen
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 5aa2d8a39be47d9affb97c3b60e53c4722c63cce
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249813"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Von WPF zu System.Xaml migrierte Typen

In .NET Framework 3.5 und .NET Framework 3.0 enthielten sowohl Windows Presentation Foundation (WPF) als auch Windows Workflow Foundation eine XAML-Sprachimplementierung. Viele der öffentlichen Typen, die Erweiterbarkeit für die WPF-XAML-Implementierung bereitstellten, waren in den WindowsBase-, PresentationCore- und PresentationFramework-Assemblys vorhanden. Ebenso existierten öffentliche Typen, die Erweiterbarkeit für Windows Workflow Foundation XAML ermöglichten, in der Assembly System.Workflow.ComponentModel. In .NET Framework 4 wurden einige der XAML-bezogenen Typen in die System.Xaml-Assembly migriert. Eine gemeinsame .NET Framework-Implementierung von XAML-Sprachdiensten ermöglicht viele XAML-Erweiterbarkeitsszenarien, die ursprünglich durch die XAML-Implementierung eines bestimmten Frameworks definiert wurden, aber jetzt Teil der allgemeinen .NET Framework 4 XAML-Sprachunterstützung sind. In diesem Artikel werden die Typen aufgeführt, die migriert wurden, und es werden Probleme im Zusammenhang mit der Migration erläutert.

## <a name="assemblies-and-namespaces"></a>Assemblys und Namespaces

In .NET Framework 3.5 und .NET Framework 3.0 befanden sich die Typen, die WPF zur Unterstützung von XAML implementiert hat, im Allgemeinen im <xref:System.Windows.Markup> Namespace. Die meisten dieser Typen befanden sich in der WindowsBase-Assembly.

In .NET Framework 4 gibt <xref:System.Xaml> es einen neuen Namespace und eine neue System.Xaml-Assembly. Viele der Typen, die ursprünglich für WPF-XAML implementiert wurden, stehen jetzt als Erweiterbarkeitspunkte oder -dienste für alle XAML-Implementierungen zur Verfügung. Im Rahmen der Verfügbarmachung für allgemeinere Szenarien wird für die Typen eine Typweiterleitung von der ursprünglichen WPF-Assembly zur System.Xaml-Assembly durchgeführt. Dadurch werden XAML-Erweiterbarkeitsszenarien aktiviert, ohne die Assemblys anderer Frameworks (z. B. WPF und Windows Workflow Foundation) einschließen zu müssen.

Für migrierte Typen verbleiben die meisten Typen im <xref:System.Windows.Markup> -Namespace. Dadurch sollte u. a. vermieden werden, dass CLR-Namespacezuordnungen in vorhandenen Implementierungen pro Datei unterbrochen werden. Daher enthält der <xref:System.Windows.Markup> Namespace in .NET Framework 4 eine Mischung aus allgemeinen XAML-Sprachunterstützungstypen (aus der System.Xaml-Assembly) und Typen, die für die WPF XAML-Implementierung spezifisch sind (von WindowsBase und anderen WPF-Assemblys). Für jeden Typ, der zu System.Xaml migriert wurde, aber zuvor in einer WPF-Assembly vorhanden war, wird in Version 4 der WPF-Assembly die Typweiterleitung unterstützt.

### <a name="workflow-xaml-support-types"></a>XAML-Unterstützungstypen in Workflow

Windows Workflow Foundation stellte auch XAML-Supporttypen bereit, die in vielen Fällen identische Kurznamen wie ein WPF-Äquivalent hatten. Im Folgenden finden Sie eine Liste der XAML-Unterstützungstypen von Windows Workflow Foundation:

- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>

Diese Supporttypen sind weiterhin in den Windows Workflow Foundation-Assemblys für .NET Framework 4 vorhanden und können weiterhin für bestimmte Windows Workflow Foundation-Anwendungen verwendet werden. Sie sollten jedoch nicht von Anwendungen oder Frameworks referenziert werden, die Windows Workflow Foundation nicht verwenden.

## <a name="markupextension"></a>MarkupExtension

In .NET Framework 3.5 und .NET Framework <xref:System.Windows.Markup.MarkupExtension> 3.0 befand sich die Klasse für WPF in der WindowsBase-Assembly. Eine parallele Klasse für <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>Windows Workflow Foundation , existierte in der Assembly System.Workflow.ComponentModel. In .NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> wird die Klasse zur System.Xaml-Assembly migriert. In .NET Framework <xref:System.Windows.Markup.MarkupExtension> 4 ist für jedes XAML-Erweiterbarkeitsszenario vorgesehen, das .NET XAML-Dienste verwendet, nicht nur für diejenigen, die auf bestimmten Frameworks aufbauen. Nach Möglichkeiten sollten auch spezifische Frameworks oder Benutzercode im Framework auf der <xref:System.Windows.Markup.MarkupExtension> -Klasse für die XAML-Erweiterung aufbauen.

## <a name="markupextension-supporting-service-classes"></a>Dienstklassen, die MarkupExtension unterstützen

.NET Framework 3.5 und .NET Framework 3.0 für WPF stellten mehrere Dienste bereit, die <xref:System.Windows.Markup.MarkupExtension> Für Implementierer und <xref:System.ComponentModel.TypeConverter> Implementierungen verfügbar waren, um die Typ-/Eigenschaftsnutzung in XAML zu unterstützen. Es handelt sich dabei um die folgenden Dienste:

- <xref:System.Windows.Markup.IProvideValueTarget>

- <xref:System.Windows.Markup.IUriContext>

- <xref:System.Windows.Markup.IXamlTypeResolver>

> [!NOTE]
> Ein weiterer Dienst von .NET Framework 3.5, <xref:System.Windows.Markup.IReceiveMarkupExtension> der sich auf Markuperweiterungen bezieht, ist die Schnittstelle. <xref:System.Windows.Markup.IReceiveMarkupExtension>wurde nicht migriert `[Obsolete]` und ist für .NET Framework 4 markiert. Für Szenarios, in denen zuvor <xref:System.Windows.Markup.IReceiveMarkupExtension> verwendet wurde, sollten stattdessen attributierte <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> -Rückrufe verwendet werden. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> ist ebenfalls als `[Obsolete]`gekennzeichnet.

## <a name="xaml-language-features"></a>Features der XAML-Sprache

Mehrere Features und Komponenten der XAML-Sprache für WPF waren zuvor in der PresentationFramework-Assembly enthalten. Diese wurden als <xref:System.Windows.Markup.MarkupExtension> -Unterklasse implementiert, damit Markuperweiterungen in XAML-Markup verwendet werden konnten. In .NET Framework 4 sind diese in der System.Xaml-Assembly vorhanden, sodass Projekte, die keine WPF-Assemblys enthalten, diese XAML-Sprachfeatures verwenden können. WPF verwendet dieselben Implementierungen für .NET Framework 4-Anwendungen. Wie in den anderen in diesem Thema aufgeführten Fällen sind die unterstützenden Typen weiterhin im <xref:System.Windows.Markup> -Namespace vorhanden, um zu verhindern, dass frühere Verweise ungültig werden.

Die folgende Tabelle enthält eine Liste der Klassen mit XAML-Featureunterstützung, die in System.Xaml definiert sind.

|Feature der XAML-Sprache|Verwendung|
|---------------------------|-----------|
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|

Obwohl System.Xaml möglicherweise keine spezifischen Unterstützungsklassen enthält, befindet sich die allgemeine Logik für die Verarbeitung von Sprachfeatures für die XAML-Sprache jetzt in System.Xaml und den zugehörigen implementierten XAML-Readern und XAML-Writern. Beispiel: `x:TypeArguments` ist ein Attribut, das von XAML-Readern und XAML-Writern aus System.Xaml-Implementierungen verarbeitet wird; es kann im XAML-Knotenstream eingetragen werden, verfügt über Behandlung im standardmäßigen (CLR-basierten) XAML-Schemakontext, hat eine XAML-Typsystemdarstellung usw. Daher ist die Referenzdokumentation für alle XAML-Sprachfeatures ein Unterthema für [XAML-Dienste](../../../desktop-wpf/xaml-services/index.md) im [Desktop-Handbuch für Windows Presentation Foundation (WPF)](../../../desktop-wpf/overview/index.md).

## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer und unterstützende Klassen

Die <xref:System.Windows.Markup.ValueSerializer> -Klasse unterstützt die Typkonvertierung in eine Zeichenfolge, insbesondere für XAML-Serialisierungsfälle, in denen die Serialisierung möglicherweise mehrere Modi oder Knoten in der Ausgabe erfordert. In .NET Framework 3.5 und .NET <xref:System.Windows.Markup.ValueSerializer> Framework 3.0 befand sich die for WPF in der WindowsBase-Assembly. In .NET Framework 4 <xref:System.Windows.Markup.ValueSerializer> befindet sich die Klasse in System.Xaml und ist für jedes XAML-Erweiterbarkeitsszenario gedacht, nicht nur für diejenigen, die auf WPF aufbauen. <xref:System.Windows.Markup.IValueSerializerContext> (ein unterstützender Dienst) und <xref:System.Windows.Markup.DateTimeValueSerializer> (eine bestimmte Unterklasse) werden ebenfalls zu „System.Xaml“ migriert.

## <a name="xaml-related-attributes"></a>XAML-bezogene Attribute

WPF-XAML enthielt mehrere Attribute, die auf CLR-Typen angewendet werden können, um Angaben über deren XAML-Verhalten zu machen. Im Folgenden finden Sie eine Liste der Attribute, die in WPF-Assemblys in .NET Framework 3.5 und .NET Framework 3.0 vorhanden waren. Diese Attribute werden in .NET Framework 4 nach System.Xaml migriert.

- <xref:System.Windows.Markup.AmbientAttribute>

- <xref:System.Windows.Markup.ContentPropertyAttribute>

- <xref:System.Windows.Markup.ContentWrapperAttribute>

- <xref:System.Windows.Markup.DependsOnAttribute>

- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

- <xref:System.Windows.Markup.NameScopePropertyAttribute>

- <xref:System.Windows.Markup.RootNamespaceAttribute>

- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

- <xref:System.Windows.Markup.ValueSerializerAttribute>

- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

- <xref:System.Windows.Markup.XmlLangPropertyAttribute>

- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

- <xref:System.Windows.Markup.XmlnsPrefixAttribute>

## <a name="miscellaneous-classes"></a>Verschiedene Klassen

Die <xref:System.Windows.Markup.IComponentConnector> Schnittstelle existierte in WindowsBase in .NET Framework 3.5 und .NET Framework 3.0, aber in System.Xaml in .NET Framework 4. <xref:System.Windows.Markup.IComponentConnector> ist hauptsächlich für Toolunterstützung und XAML-Markupcompiler gedacht.

Die <xref:System.Windows.Markup.INameScope> Schnittstelle existierte in WindowsBase in .NET Framework 3.5 und .NET Framework 3.0, aber in System.Xaml in .NET Framework 4. <xref:System.Windows.Markup.INameScope> definiert grundlegende Vorgänge für einen XAML-Namensbereich.

## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>XAML-bezogene Klassen mit freigegebenen Namen, die in WPF und System.Xaml vorhanden sind

Die folgenden Klassen sind sowohl in den WPF-Assemblys als auch in der System.Xaml-Assembly in .NET Framework 4 vorhanden:

`XamlReader`

`XamlWriter`

`XamlParseException`

Die WPF-Implementierung befindet sich im <xref:System.Windows.Markup> -Namespace und in der PresentationFramework-Assembly. Die System.Xaml-Implementierung befindet sich im <xref:System.Xaml> -Namespace. Wenn Sie WPF-Typen verwenden oder von WPF-Typen ableiten, sollten Sie in der Regel die WPF-Implementierungen von <xref:System.Windows.Markup.XamlReader> und <xref:System.Windows.Markup.XamlWriter> anstelle der System.Xaml-Implementierungen verwenden. Weitere Informationen finden Sie in den Bemerkungen zu <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> und <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.

Wenn Sie Verweise auf WPF-Assemblys und System.Xaml einschließen und außerdem `include` -Anweisungen für den <xref:System.Windows.Markup> - und den <xref:System.Xaml> -Namespace verwenden, müssen Sie die Aufrufe dieser APIs möglicherweisemöglicherweise vollständig qualifizieren, um die Typen ohne Mehrdeutigkeit aufzulösen.
