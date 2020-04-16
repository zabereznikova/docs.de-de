---
title: x:Statische Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433265"
---
# <a name="xstatic-markup-extension"></a>x:Statische Markuperweiterung

Verweist auf jede statische Codeentität mit Nebenwert, die auf CLS-konform (Common Language Specification) definiert ist. Die statische Eigenschaft, auf die verwiesen wird, kann verwendet werden, um den Wert einer Eigenschaft in XAML bereitzustellen.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a>XAML-Werte

| | |
|-|-|
|`prefix`|Optional. Ein Präfix, das auf einen zugeordneten, nicht standardmäßigen XAML-Namespace verweist. `prefix`wird explizit in der Verwendung angezeigt, da Sie selten auf statische Eigenschaften verweisen, die aus einem standardmäßigen XAML-Namespace stammen. Siehe Hinweise.|
|`typeName`|Erforderlich. Der Name des Typs, der den gewünschten statischen Member definiert.|
|`staticMemberName`|Erforderlich. Der Name des gewünschten statischen Wertelements (eine Konstante, eine statische Eigenschaft, ein Feld oder ein Enumerationswert).|

## <a name="remarks"></a>Bemerkungen

Die Codeentität, auf die verwiesen wird, muss eine der folgenden sein:

- Eine Konstante
- Eine statische Eigenschaft
- Ein Feld
- Ein Enumerationswert

Das Angeben einer anderen Codeentität, z. B. einer nicht statischen Eigenschaft, verursacht einen Kompilierungsfehler, wenn das XAML Markup kompiliert wird, oder eine XAML-Ausnahme für die Lastzeitanalyse.

Sie können `x:Static` Verweise auf statische Felder oder Eigenschaften erstellen, die nicht im Standard-XAML-Namespace für das aktuelle XAML-Dokument enthalten sind. Dies erfordert jedoch eine Präfixzuordnung. XAML-Namespaces werden fast immer im Stammelement des XAML-Dokuments definiert.

Die Suchvorgänge für statische Eigenschaften können von .NET XAML Services und seinen XAML-Readern und XAML-Writern ausgeführt werden, wenn sie mit dem standardmäßigen XAML-Schemakontext ausgeführt werden. Dieser XAML-Schemakontext kann CLR-Reflektion verwenden, um die erforderlichen statischen Werte für die Objektdiagrammerstellung bereitzustellen. Der `typeName` von Ihnen angegebene Name ist eigentlich ein XAML-Typname und kein CLR-Typname, obwohl diese im Wesentlichen derselbe Name sind, wenn sie den standardmäßigen XAML-Schemakontext verwenden oder alle vorhandenen CLAML-basierten XAML-implementierenden Frameworks verwenden.

Seien Sie vorsichtig, wenn Sie Verweise vornehmen, `x:Static` die nicht direkt der Typ des Werts einer Eigenschaft sind. In der XAML-Verarbeitungssequenz rufen bereitgestellte Werte aus einer Markuperweiterung keine zusätzliche Wertkonvertierung auf. Dies gilt auch `x:Static` dann, wenn Ihr Verweis eine Textzeichenfolge erstellt und eine Wertkonvertierung für Attributwerte basierend auf Textzeichenfolge nmöglich entweder für dieses bestimmte Element oder für Elementwerte des Rückgabetyps erfolgt.

Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Static`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.StaticExtension.Member%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.StaticExtension>-Erweiterungsklasse zugeordnet.

Es gibt zwei weitere XAML-Verwendungen, die technisch möglich sind. Diese Verwendungen sind jedoch seltener, da sie unnötig ausführlich sind:

01. Objektelementsyntax.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. Attributsyntax mit expliziter Member-Eigenschaft für Initialisierungszeichenfolge.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

In der .NET XAML Services-Implementierung wird die Verarbeitung <xref:System.Windows.Markup.StaticExtension> für diese Markuperweiterung von der Klasse definiert.

`x:Static` ist eine Markuperweiterung. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in ihrer Attributsyntax, d. h. der Konvention, nach der ein XAML-Prozessor erkennt, dass eine Markuperweiterung einen Wert bereitstellen muss. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-overview.md).

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Der standardmäßige XAML-Namespace, den Sie für die WPF-Programmierung verwenden, enthält nicht viele nützliche statische Eigenschaften, `{x:Static}` und die meisten nützlichen statischen Eigenschaften unterstützen z. B. Typkonverter, die die Verwendung ohne die Verwendung erleichtern. Für statische Eigenschaften müssen Sie ein Präfix für einen XAML-Namespace zuordnen, wenn eine der folgenden Optionen zutrifft:

- Sie verweisen auf einen Typ, der in WPF vorhanden ist, aber nicht Teil`http://schemas.microsoft.com/winfx/2006/xaml/presentation`des standardmäßigen XAML-Namespace für WPF ( ) ist. Dies ist ein ziemlich `x:Static`häufiges Szenario für die Verwendung von . Sie können z. `x:Static` B. einen Verweis mit einer <xref:System> XAML-Namespacezuordnung zum CLR-Namespace und <xref:System.Environment> zur mscorlib-Assembly verwenden, um auf die statischen Eigenschaften der Klasse zu verweisen.

- Sie verweisen auf einen Typ aus einer benutzerdefinierten Assembly.

- Sie verweisen auf einen Typ, der in einer WPF-Assembly vorhanden ist, dieser Typ befindet sich jedoch in einem CLR-Namespace, der nicht als Teil des WPF-Standard-XAML-Namespace zugeordnet wurde. Die Zuordnung von CLR-Namespaces zum Standardmäßigen XAML-Namespace für WPF wird durch Definitionen in den verschiedenen WPF-Assemblys durchgeführt (weitere Informationen zu diesem Konzept finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Nicht zugeordnete CLR-Namespaces können vorhanden sein, wenn dieser CLR-Namespace hauptsächlich aus Klassendefinitionen <xref:System.Windows.Threading>besteht, die normalerweise nicht für XAML vorgesehen sind, z. B. .

Weitere Informationen zur Verwendung von Präfixen und XAML-Namespaces für WPF finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

## <a name="see-also"></a>Weitere Informationen

- [x:Type-Markuperweiterung](xtype-markup-extension.md)
- [Aus WPF zu System.Xaml migrierte Typen](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
