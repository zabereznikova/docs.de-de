---
title: Typkonverter und Markuperweiterungen für XAML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], type converter services
- XAML [XAML Services], value converters
- XAML [XAML Services], markup extension services
- value converters for XAML [XAML Services]
- XAML [XAML Services], service context
ms.assetid: db07a952-05ce-4aa4-b6f9-aac7397d0326
caps.latest.revision: 13
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 34d48e7de0269449bd4ed6eedb83a7464b6d3d50
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="type-converters-and-markup-extensions-for-xaml"></a>Typkonverter und Markuperweiterungen für XAML
Typkonverter und Markuperweiterung sind zwei Techniken, mit denen XAML-Typsysteme und XAML-Writer Objektdiagrammkomponenten generieren. Obwohl sie einige gemeinsame Eigenschaften aufweisen, werden Typkonverter und Markuperweiterungen in einem XAML-Knotenstream unterschiedlich dargestellt. In dieser Dokumentation werden Typkonverter, Markuperweiterungen und ähnliche Konstrukte manchmal zusammenfassend als Wertkonverter bezeichnet.  
  
<a name="value_converters"></a>   
## <a name="value-converters"></a>Wertkonverter  
 In XAML werden Wertkonverter für verschiedene Szenarien verwendet. Die folgende Liste enthält die verschiedenen Arten von Wertkonvertern im XAML:  
  
-   Typkonverter  
  
-   Markuperweiterung  
  
-   Werte-Serialisierungsprogramm  
  
-   Verwandte Klasse oder Unterstützungsklasse, die die Logik für eine XAML-Textsyntax bereitstellt  
  
<a name="type_converters"></a>   
## <a name="type-converters"></a>Typkonverter  
 In der Definition der .NET Framework-XAML-Dienste sind Typkonverter von der CLR- <xref:System.ComponentModel.TypeConverter> -Klasse abgeleitete Klassen. <xref:System.ComponentModel.TypeConverter> ist eine Klasse, die es in [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] gab, bevor XAML verfügbar war. Der ursprüngliche Zweck war, Eigenschaftenfenster und ähnliche textbasierte Bearbeitungsmetaphern für [!INCLUDE[TLA2#tla_ide](../../../includes/tla2sharptla-ide-md.md)] -Eigenschaften zu unterstützen. Die Einführung von XAML in .NET Framework verwendet <xref:System.ComponentModel.TypeConverter> zum Konvertieren einer Textsyntax (wie sie in einem Attributwert oder XAML-Wertknoten zu finden ist) in ein Objekt. <xref:System.ComponentModel.TypeConverter> kann auch zum Serialisieren eines Objektwerts in Textsyntax verwendet werden. <xref:System.ComponentModel.TypeConverter> wurde auch in früheren Framework-spezifischen XAML-Implementierungen in verwendet [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] und Windows Communication Foundation (WCF). Weitere Informationen zum <xref:System.ComponentModel.TypeConverter> in XAML finden Sie unter [Type Converters for XAML Overview](../../../docs/framework/xaml-services/type-converters-for-xaml-overview.md)verwendet.  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Markuperweiterungen  
 In der Implementierung der .NET Framework-XAML-Dienste sind Markuperweiterungen von der <xref:System.Windows.Markup.MarkupExtension> -Klasse abgeleitete Klassen. Markuperweiterungen sind ein Konzept, das in dieser Form aus der XAML-Sprache entstanden ist. Stellen Sie sich eine Markuperweiterung in etwa als eine erweiterbare Escapesequenz vor, die eine Dienstklasse aufruft, um ihre Logik bereitzustellen. Im Hinblick auf Markup erkennen XAML-Prozessoren universell eine Markuperweiterung anhand einer Textsequenz, die mit einer öffnenden geschweiften Klammer ({) in einer Textzeichenfolge beginnt.  
  
 Markuperweiterungen unterscheiden sich von Typkonvertern. Typkonverter sind normalerweise Typen oder Membern zugeordnet. Sie werden aufgerufen, wenn bei der Erstellung eines Objektdiagramms oder einer Serialisierung eine Textsyntax gefunden wird, die solchen Entitäten zugeordnet ist.  
  
 Markuperweiterungen sind einer einzelnen unterstützenden Dienstklasse zugeordnet, können aber für jeden Memberwert angewendet werden. (Allerdings können Sie die Markuperweiterung so implementieren, dass ihre Verwendung mithilfe von Dienstkontext bewusst auf bestimmte Member oder Zieltypen eingeschränkt wird.) Markuperweiterungen können die Zuordnung eines Typkonverters überschreiben. Oder Sie können sie verwenden, um einen Attributwert für Member anzugeben, die eine Textsyntax andernfalls nicht unterstützen würden.  
  
 Weitere Informationen zu den Implementierungsmustern für Markuperweiterungen für XAML finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
> [!NOTE]
>  Die Typen <xref:System.Windows.Markup.MarkupExtension> und <xref:System.Windows.Markup.ValueSerializer> befinden sich beide im <xref:System.Windows.Markup> -Namespace und nicht im <xref:System.Xaml> -Namespace. Dies bedeutet nicht, dass diese Typen für die WPF- oder Windows Forms-Technologien spezifisch sind, die andernfalls CLR-Namespaces auffüllen, die die Zeichenfolge enthalten `Windows`. <xref:System.Windows.Markup.MarkupExtension> und <xref:System.Windows.Markup.ValueSerializer> befinden sich in der System.Xaml-Assembly und weisen keine spezifische Framework-Abhängigkeit auf. Diese Typen waren im CLR-Namespace für [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] vorhanden und bleiben im CLR-Namespace in [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] erhalten, um zu vermeiden, dass Verweise in vorhandenen WPF-Projekten getrennt werden. Weitere Informationen finden Sie unter [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md).  
  
<a name="value_serializers"></a>   
## <a name="value-serializers"></a>Werte-Serialisierungsprogramme  
 Ein <xref:System.Windows.Markup.ValueSerializer> ist ein spezialisierter Typkonverter, der zum Konvertieren eines Objekts in eine Zeichenfolge optimiert ist. Ein <xref:System.Windows.Markup.ValueSerializer> für XAML implementiert die `ConvertFrom` -Methode möglicherweise überhaupt nicht. Eine <xref:System.Windows.Markup.ValueSerializer> -Implementierung ruft Dienste auf eine Weise auf, die einer <xref:System.ComponentModel.TypeConverter> -Implementierung gleicht. Die virtuellen Methoden bieten einen Eingabe-`context`-Parameter. Der `context` -Parameter ist vom Typ <xref:System.Windows.Markup.IValueSerializerContext>, der von der <xref:System.IServiceProvider> -Schnittstelle erbt und über eine <xref:System.IServiceProvider.GetService%2A> -Methode verfügt.  
  
 Im XAML-Typsystem und für XAML-Writer-Implementierungen, die die Verarbeitung von XAML-Knotenschleifen für die Serialisierung verwenden, wird ein Wertkonverter, der einem Typ oder Member zugeordnet ist, durch seine eigene <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType>-Eigenschaft gemeldet. Die Bedeutung für XAML-Writer, die Serialisierungen durchführen, ist, dass wenn ein <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> und <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> vorhanden sind, der Typkonverter für den Pfad zum Laden verwendet werden sollte und das Werte-Serialisierungsprogramm für den Pfad zum Speichern. Wenn <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> vorhanden ist, aber <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> `null` ist, wird der Typkonverter auch für den Pfad zum Speichern verwendet.  
  
<a name="other_value_converters"></a>   
## <a name="other-value-converters"></a>Andere Wertkonverter  
 Ein Wertkonverter kann über die spezifischen Muster eines Typkonverters oder einer Markuperweiterungen hinaus erweitert werden. Diese Anpassung erfordert jedoch auch die Neudefinition des XAML-Typsystem entsprechend der Bereitstellung durch .NET Framework-XAML-Dienste. Das vorhandene XAML-Typsystem verfügt über Darstellungen und Berichtssysteme für Typkonverter, Markuperweiterungen und Werte-Serialisierungsprogramme, jedoch nicht für benutzerdefinierte Formen der Wertkonvertierung. Wenn Sie benutzerdefinierte Wertkonverter erstellen möchten, verwenden Sie den <xref:System.Xaml.Schema.XamlValueConverter%601> -Typ.  
  
<a name="type_converters_and_markup_extensions_in_combination"></a>   
## <a name="type-converters-and-markup-extensions-in-combination"></a>Typkonverter und Markuperweiterungen kombiniert  
 Markuperweiterungen und Typkonverter werden für verschiedene Situationen in XAML verwendet. Obwohl der Kontext für die Verwendung von Markuperweiterungen verfügbar ist, wird das Typkonvertierungsverhalten von Eigenschaften, bei denen eine Markuperweiterung einen Wert bereitstellt, in der Regel nicht in den Implementierungen der Markuperweiterung überprüft. Mit anderen Worten, auch wenn eine Markuperweiterung eine Textzeichenfolge als `ProvideValue` -Ausgabe zurückgibt, wird das Typkonvertierungsverhalten für diese Zeichenfolge entsprechend der Anwendung auf eine spezifische Eigenschaft oder einen spezifischen Eigenschaftswerttyp nicht aufgerufen. Im Allgemeinen besteht der Zweck einer Markuperweiterung darin, eine Zeichenfolge zu verarbeiten und ein Objekt ohne Beteiligung eines Typkonverters zurückzugeben.  
  
<a name="service_context_for_a_value_converter"></a>   
## <a name="service-context-for-a-value-converter"></a>Dienstkontext für einen Wertkonverter  
 Wenn Sie einen Wertkonverter implementieren, benötigen Sie häufig Zugriff auf einen Kontext, in dem der Wertkonverter angewendet wird. Dieser Kontext wird als Dienstkontext bezeichnet. Der Kontext kann Informationen wie z. B. den aktiven XAML-Schemakontext, den Zugriff auf das Typzuordnungssystem, das der XAML-Schemakontext und der XAML-Objektwriter bereitstellen, usw. enthalten. Weitere Informationen zu den für einen Wertkonverter verfügbaren Dienstkontexten sowie dazu, wie auf die Dienste zugegriffen wird, die ein Dienstkontext bereitstellen kann, finden Sie unter [Service Contexts Available to Type Converters and Markup Extensions](../../../docs/framework/xaml-services/service-contexts-available-to-type-converters-and-markup-extensions.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Markup.MarkupExtension>  
 <xref:System.Xaml.XamlObjectWriter>  
 [Übersicht über Markuperweiterungen für XAML](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)  
 [Übersicht über Typkonverter für XAML](../../../docs/framework/xaml-services/type-converters-for-xaml-overview.md)  
 [Für Typkonverter und Markuperweiterungen verfügbare Dienstkontexte](../../../docs/framework/xaml-services/service-contexts-available-to-type-converters-and-markup-extensions.md)
