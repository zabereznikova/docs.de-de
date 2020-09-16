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
ms.openlocfilehash: 634a480b4d7446ed09708f6c91276d1c2f61d4a9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551610"
---
# <a name="xstatic-markup-extension"></a>x:Statische Markuperweiterung

Verweist auf eine beliebige statische Code Entität, die in einer Common Language Specification (CLS) – kompatiblen Weise definiert ist. Die statische Eigenschaft, auf die verwiesen wird, kann verwendet werden, um den Wert einer Eigenschaft in XAML bereitzustellen.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a>XAML-Werte

| | |
|-|-|
|`prefix`|Dies ist optional. Ein Präfix, das auf einen zugeordneten, nicht standardmäßigen XAML-Namespace verweist. `prefix` wird explizit in der Verwendung angezeigt, da Sie selten auf statische Eigenschaften verweisen, die von einem XAML-Standard Namespace stammen. Siehe Hinweise.|
|`typeName`|Erforderlich. Der Name des Typs, der den gewünschten statischen Member definiert.|
|`staticMemberName`|Erforderlich. Der Name des gewünschten statischen Wertmembers (eine Konstante, eine statische Eigenschaft, ein Feld oder ein Enumerationswert).|

## <a name="remarks"></a>Hinweise

Die Code Entität, auf die verwiesen wird, muss eine der folgenden sein:

- Eine Konstante
- Eine statische Eigenschaft
- Ein Feld
- Ein Enumerationswert.

Das Angeben einer anderen Code Entität, z. b. einer nicht statischen Eigenschaft, verursacht einen Kompilierzeitfehler, wenn XAML Markup kompiliert ist, oder eine XAML-Auslastungs Analyse Ausnahme.

Sie können `x:Static` Verweise auf statische Felder oder Eigenschaften erstellen, die sich nicht im XAML-Standard Namespace für das aktuelle XAML-Dokument befinden; dies erfordert jedoch eine Präfix Zuordnung. XAML-Namespaces werden fast immer für das Stamm Element des XAML-Dokuments definiert.

Die Suchvorgänge für statische Eigenschaften können von .net XAML-Diensten und deren XAML-Readern und XAML-Writern ausgeführt werden, wenn Sie mit dem standardmäßigen XAML-Schema Kontext ausgeführt werden. Dieser XAML-Schema Kontext kann die CLR-Reflektion verwenden, um die erforderlichen statischen Werte für die Objekt Diagramm Erstellung bereitzustellen. Der von `typeName` Ihnen angegebene ist tatsächlich ein XAML-Typname und kein CLR-Typname, obwohl diese im Wesentlichen denselben Namen haben, wenn Sie den standardmäßigen XAML-Schema Kontext verwenden oder alle vorhandenen CLR-basierten XAML-implementierenden Frameworks verwenden.

Gehen Sie vorsichtig `x:Static` vor, wenn Sie Verweise erstellen, die nicht direkt der Typ des Eigenschafts Werts sind. In der XAML-Verarbeitungssequenz rufen bereitgestellte Werte aus einer Markup Erweiterung keine zusätzliche Wert Konvertierung auf. Dies gilt auch, wenn der `x:Static` Verweis eine Text Zeichenfolge erstellt und eine Wert Konvertierung für Attributwerte, die auf der Text Zeichenfolge basieren, in der Regel entweder für dieses bestimmte Element oder für beliebige Element Werte des Rückgabe Typs auftritt.

Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Static`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.StaticExtension.Member%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.StaticExtension>-Erweiterungsklasse zugeordnet.

Es gibt zwei andere XAML-Verwendungen, die technisch möglich sind. Diese Verwendungen sind jedoch weniger häufig, da sie unnötig ausführlich sind:

01. Objekt Element Syntax.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. Attribut Syntax mit expliziter Element Eigenschaft für die Initialisierungs Zeichenfolge.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

In der .net XAML Services-Implementierung wird die Handhabung dieser Markup Erweiterung durch die- <xref:System.Windows.Markup.StaticExtension> Klasse definiert.

`x:Static` ist eine Markuperweiterung. Alle Markup Erweiterungen in XAML verwenden die `{` `}` Zeichen und in der Attribut Syntax. Dies ist die Konvention, mit der ein XAML-Prozessor erkennt, dass eine Markup Erweiterung einen Wert bereitstellen muss. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-overview.md).

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

Der standardmäßige XAML-Namespace, den Sie für die WPF-Programmierung verwenden, enthält nicht viele nützliche statische Eigenschaften, und die meisten nützlichen statischen Eigenschaften haben Unterstützung, wie z. b. Typkonverter, die die Verwendung ohne Anforderung vereinfachen `{x:Static}` . Für statische Eigenschaften müssen Sie ein Präfix für einen XAML-Namespace zuordnen, wenn einer der folgenden Punkte zutrifft:

- Sie verweisen auf einen Typ, der in WPF vorhanden ist, aber nicht Teil des standardmäßigen XAML-Namespace für WPF ( `http://schemas.microsoft.com/winfx/2006/xaml/presentation` ) ist. Dies ist ein gängiges Szenario für die Verwendung von `x:Static` . Sie können z. b. einen `x:Static` Verweis mit einer XAML-Namespace Zuordnung zur <xref:System> CLR-Namespace-und mscorlib-Assembly verwenden, um auf die statischen Eigenschaften der-Klasse zu verweisen <xref:System.Environment> .

- Sie verweisen auf einen Typ aus einer benutzerdefinierten Assembly.

- Sie verweisen auf einen Typ, der in einer WPF-Assembly vorhanden ist. dieser Typ befindet sich jedoch innerhalb eines CLR-Namespace, der nicht als Teil des WPF-XAML-Standard Namespace zugeordnet wurde. Die Zuordnung von CLR-Namespaces in den XAML-Standard Namespace für WPF erfolgt durch Definitionen in den verschiedenen WPF-Assemblys (Weitere Informationen zu diesem Konzept finden Sie unter [XAML-Namespaces und Namespace Zuordnung für WPF-XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml)). Nicht zugeordnete CLR-Namespaces können vorhanden sein, wenn dieser CLR-Namespace hauptsächlich aus Klassendefinitionen besteht, die in der Regel nicht für XAML vorgesehen sind, z <xref:System.Windows.Threading> . b..

Weitere Informationen zur Verwendung von Präfixen und XAML-Namespaces für WPF finden Sie unter [XAML-Namespaces und Namespace Zuordnung für WPF-XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).

## <a name="see-also"></a>Siehe auch

- [x:Type-Markuperweiterung](xtype-markup-extension.md)
- [Aus WPF zu System.Xaml migrierte Typen](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
