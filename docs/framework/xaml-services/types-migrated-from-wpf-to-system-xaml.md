---
title: Aus WPF zu System.Xaml migrierte Typen
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 943cdb2a21cbf2f95ef7fe2feefe6c0e71f57be4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939679"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Aus WPF zu System.Xaml migrierte Typen
In .NET Framework 3,5 und .NET Framework 3,0 enthielt sowohl [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] als auch Windows Workflow Foundation eine XAML-sprach Implementierung. Viele der öffentlichen Typen, die Erweiterbarkeit für die WPF-XAML-Implementierung bereitstellten, waren in den WindowsBase-, PresentationCore- und PresentationFramework-Assemblys vorhanden. Ebenso waren öffentliche Typen, die Erweiterbarkeit für Windows Workflow Foundation XAML bereitstellten, in der System. Workflow. ComponentModel-Assembly vorhanden. In den .NET Framework 4 werden einige der XAML-bezogenen Typen zur System. XAML-Assembly migriert. Eine gängige .NET Framework Implementierung der XAML-Sprachdienste ermöglicht viele XAML-Erweiterbarkeits Szenarios, die ursprünglich durch die XAML-Implementierung eines bestimmten Frameworks definiert wurden, aber jetzt Teil der gesamten .NET Framework 4 XAML-Sprachunterstützung sind. In diesem Thema werden die migrierten Typen aufgeführt und Probleme im Zusammenhang mit der Migration erläutert.  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a>Assemblys und Namespaces  
 In .NET Framework 3,5 und .NET Framework 3,0 waren die Typen, die WPF zur Unterstützung von XAML implementiert hat <xref:System.Windows.Markup> , in der Regel im-Namespace. Die meisten dieser Typen befanden sich in der WindowsBase-Assembly.  
  
 In .NET Framework 4 gibt es einen neuen <xref:System.Xaml> Namespace und eine neue System. XAML-Assembly. Viele der Typen, die ursprünglich für WPF-XAML implementiert wurden, stehen jetzt als Erweiterbarkeitspunkte oder -dienste für alle XAML-Implementierungen zur Verfügung. Im Rahmen der Verfügbarmachung für allgemeinere Szenarien wird für die Typen eine Typweiterleitung von der ursprünglichen WPF-Assembly zur System.Xaml-Assembly durchgeführt. Dies ermöglicht XAML-Erweiterbarkeits Szenarios, ohne dass die Assemblys anderer Frameworks (z. b. WPF und Windows Workflow Foundation) eingeschlossen werden müssen.  
  
 Für migrierte Typen verbleiben die meisten Typen im <xref:System.Windows.Markup> -Namespace. Dadurch sollte u. a. vermieden werden, dass CLR-Namespacezuordnungen in vorhandenen Implementierungen pro Datei unterbrochen werden. Daher enthält der <xref:System.Windows.Markup> Namespace in .NET Framework 4 eine Mischung aus allgemeinen XAML-sprach Unterstützungs Typen (aus der System. XAML-Assembly) und Typen, die für die WPF-XAML-Implementierung spezifisch sind (aus Windows Base und anderen WPF-Assemblys). Für jeden Typ, der zu System.Xaml migriert wurde, aber zuvor in einer WPF-Assembly vorhanden war, wird in Version 4 der WPF-Assembly die Typweiterleitung unterstützt.  
  
### <a name="workflow-xaml-support-types"></a>XAML-Unterstützungstypen in Workflow  
 Windows Workflow Foundation auch XAML-Unterstützungs Typen bereitgestellt, und in vielen Fällen hatten diese die gleichen Kurznamen wie eine WPF-Entsprechung. Im folgenden finden Sie eine Liste der Windows Workflow Foundation XAML-Unterstützungs Typen:  
  
- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 Diese Unterstützungs Typen sind immer noch in den Windows Workflow Foundation Assemblys für .NET Framework 4 vorhanden und können weiterhin für bestimmte Windows Workflow Foundation Anwendungen verwendet werden. Sie sollten jedoch nicht von Anwendungen oder Frameworks referenziert werden, die Windows Workflow Foundation nicht verwenden.  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a>MarkupExtension  
 In den .NET Framework 3,5 und .NET Framework 3,0 befand sich <xref:System.Windows.Markup.MarkupExtension> die-Klasse für WPF in der Windows Base-Assembly. Eine parallele Klasse für Windows Workflow Foundation, <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>, war in der System. Workflow. ComponentModel-Assembly vorhanden. In der .NET Framework 4 wird die <xref:System.Windows.Markup.MarkupExtension> -Klasse zur System. XAML-Assembly migriert. In .NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> ist für alle XAML-Erweiterbarkeits Szenarios gedacht, die .NET Framework XAML-Dienste verwenden, nicht nur für diejenigen, die auf bestimmten Frameworks aufbauen. Nach Möglichkeiten sollten auch spezifische Frameworks oder Benutzercode im Framework auf der <xref:System.Windows.Markup.MarkupExtension> -Klasse für die XAML-Erweiterung aufbauen.  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a>Dienstklassen, die MarkupExtension unterstützen  
 In .NET Framework 3,5 und .NET Framework 3,0 für WPF wurden mehrere Dienste bereitgestellt, <xref:System.Windows.Markup.MarkupExtension> die Implementierern und <xref:System.ComponentModel.TypeConverter> Implementierungen zur Unterstützung der Verwendung von Typen/Eigenschaften in XAML zur Verfügung standen. Es handelt sich dabei um die folgenden Dienste:  
  
- <xref:System.Windows.Markup.IProvideValueTarget>  
  
- <xref:System.Windows.Markup.IUriContext>  
  
- <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
> Ein anderer Dienst von .NET Framework 3,5, der sich auf Markup Erweiterungen bezieht <xref:System.Windows.Markup.IReceiveMarkupExtension> , ist die-Schnittstelle. <xref:System.Windows.Markup.IReceiveMarkupExtension>wurde nicht migriert und ist `[Obsolete]` für .NET Framework 4 markiert. Für Szenarios, in denen zuvor <xref:System.Windows.Markup.IReceiveMarkupExtension> verwendet wurde, sollten stattdessen attributierte <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> -Rückrufe verwendet werden. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> ist ebenfalls als `[Obsolete]`gekennzeichnet.  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a>Features der XAML-Sprache  
 Mehrere Features und Komponenten der XAML-Sprache für WPF waren zuvor in der PresentationFramework-Assembly enthalten. Diese wurden als <xref:System.Windows.Markup.MarkupExtension> -Unterklasse implementiert, damit Markuperweiterungen in XAML-Markup verwendet werden konnten. In .NET Framework 4 sind diese in der System. XAML-Assembly vorhanden, sodass Projekte, die keine WPF-Assemblys enthalten, diese Funktionen auf XAML-Sprachebene verwenden können. WPF verwendet die gleichen Implementierungen für .NET Framework 4-Anwendungen. Wie in den anderen in diesem Thema aufgeführten Fällen sind die unterstützenden Typen weiterhin im <xref:System.Windows.Markup> -Namespace vorhanden, um zu verhindern, dass frühere Verweise ungültig werden.  
  
 Die folgende Tabelle enthält eine Liste der Klassen mit XAML-Featureunterstützung, die in System.Xaml definiert sind.  
  
|Feature der XAML-Sprache|Verwendung|  
|---------------------------|-----------|  
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|  
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|  
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|  
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|  
  
 Obwohl System.Xaml möglicherweise keine spezifischen Unterstützungsklassen enthält, befindet sich die allgemeine Logik für die Verarbeitung von Sprachfeatures für die XAML-Sprache jetzt in System.Xaml und den zugehörigen implementierten XAML-Readern und XAML-Writern. Beispiel: `x:TypeArguments` ist ein Attribut, das von XAML-Readern und XAML-Writern aus System.Xaml-Implementierungen verarbeitet wird; es kann im XAML-Knotenstream eingetragen werden, verfügt über Behandlung im standardmäßigen (CLR-basierten) XAML-Schemakontext, hat eine XAML-Typsystemdarstellung usw. Folglich ist die Referenzdokumentation für alle Features auf XAML-Sprachebene ein untergeordnetes Thema von [XAML Services](index.md) und diesem allgemeinen Bereich der .NET Framework-Dokumentation, statt Bestandteil der WPF-Dokumentation als untergeordnetes Thema von [Erweitert (Windows Presentation Foundation)](../wpf/advanced/index.md) zu sein (was in der 3.5-Dokumentation weiterhin der Fall ist).  
  
<a name="valueserializer_and_supporting_classes"></a>   
## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer und unterstützende Klassen  
 Die <xref:System.Windows.Markup.ValueSerializer> -Klasse unterstützt die Typkonvertierung in eine Zeichenfolge, insbesondere für XAML-Serialisierungsfälle, in denen die Serialisierung möglicherweise mehrere Modi oder Knoten in der Ausgabe erfordert. In .NET Framework 3,5 und .NET Framework 3,0 befand sich <xref:System.Windows.Markup.ValueSerializer> der für WPF in der Windows Base-Assembly. In der .NET Framework 4 befindet sich <xref:System.Windows.Markup.ValueSerializer> die-Klasse in System. XAML und ist für alle XAML-Erweiterbarkeits Szenarios gedacht, nicht nur für diejenigen, die auf WPF aufbauen. <xref:System.Windows.Markup.IValueSerializerContext> (ein unterstützender Dienst) und <xref:System.Windows.Markup.DateTimeValueSerializer> (eine bestimmte Unterklasse) werden ebenfalls zu „System.Xaml“ migriert.  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a>XAML-bezogene Attribute  
 WPF-XAML enthielt mehrere Attribute, die auf CLR-Typen angewendet werden können, um Angaben über deren XAML-Verhalten zu machen. Im folgenden finden Sie eine Liste der Attribute, die in WPF-Assemblys in .NET Framework 3,5 und .NET Framework 3,0 vorhanden waren. Diese Attribute werden in .NET Framework 4 zu "System. XAML" migriert.  
  
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
  
<a name="miscellaneous_classes"></a>   
## <a name="miscellaneous-classes"></a>Verschiedene Klassen  
 Die <xref:System.Windows.Markup.IComponentConnector> -Schnittstelle war in der .NET Framework 3,5 und .NET Framework 3,0 in Windows Base vorhanden, ist jedoch in "System. XAML" in .NET Framework 4 vorhanden. <xref:System.Windows.Markup.IComponentConnector> ist hauptsächlich für Toolunterstützung und XAML-Markupcompiler gedacht.  
  
 Die <xref:System.Windows.Markup.INameScope> -Schnittstelle war in der .NET Framework 3,5 und .NET Framework 3,0 in Windows Base vorhanden, ist jedoch in "System. XAML" in .NET Framework 4 vorhanden. <xref:System.Windows.Markup.INameScope> definiert grundlegende Vorgänge für einen XAML-Namensbereich.  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>XAML-bezogene Klassen mit freigegebenen Namen, die in WPF und System.Xaml vorhanden sind  
 Die folgenden Klassen sind in den WPF-Assemblys und in der System. XAML-Assembly im .NET Framework 4 vorhanden:  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 Die WPF-Implementierung befindet sich im <xref:System.Windows.Markup> -Namespace und in der PresentationFramework-Assembly. Die System.Xaml-Implementierung befindet sich im <xref:System.Xaml> -Namespace. Wenn Sie WPF-Typen verwenden oder von WPF-Typen ableiten, sollten Sie in der Regel die WPF-Implementierungen von <xref:System.Windows.Markup.XamlReader> und <xref:System.Windows.Markup.XamlWriter> anstelle der System.Xaml-Implementierungen verwenden. Weitere Informationen finden Sie in den Bemerkungen zu <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> und <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.  
  
 Wenn Sie Verweise auf WPF-Assemblys und System.Xaml einschließen und außerdem `include` -Anweisungen für den <xref:System.Windows.Markup> - und den <xref:System.Xaml> -Namespace verwenden, müssen Sie die Aufrufe dieser APIs möglicherweisemöglicherweise vollständig qualifizieren, um die Typen ohne Mehrdeutigkeit aufzulösen.  
  
## <a name="see-also"></a>Siehe auch

- [XAML Services](index.md) (XAML-Dienste)
