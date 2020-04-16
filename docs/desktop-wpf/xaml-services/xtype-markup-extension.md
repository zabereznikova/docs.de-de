---
title: x:Type-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432635"
---
# <a name="xtype-markup-extension"></a>x:Type-Markuperweiterung

Stellt das <xref:System.Type> CLR-Objekt an, das der zugrunde liegende Typ für einen angegebenen XAML-Typ ist.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`prefix`|Optional. Ein Präfix, das einen nicht standardmäßigen XAML-Namespace zuordnet. Die Angabe eines Präfixes ist häufig nicht erforderlich. Siehe Hinweise.|
|`typeNameValue`|Erforderlich. Ein Typname, der auf den aktuellen Standard-XAML-Namespace aufgelöst werden kann. oder das angegebene zugeordnete `prefix` Präfix, wenn angegeben wird.|

## <a name="remarks"></a>Bemerkungen

Die `x:Type` Markuperweiterung hat eine `typeof()` ähnliche Funktion wie `GetType` der Operator in C- oder der Operator in Microsoft Visual Basic.

Die `x:Type` Markuperweiterung stellt ein Konvertierungsverhalten von aus <xref:System.Type>der Zeichenfolge für Eigenschaften zur Verfügung, die den Typ annehmen. Die Eingabe ist ein XAML-Typ. Die Beziehung zwischen dem Eingabe-XAML-Typ und der Ausgabe-CLR <xref:System.Type> besteht darin, dass die Ausgabe <xref:System.Type> die <xref:System.Xaml.XamlType.UnderlyingType%2A> der Eingabe <xref:System.Xaml.XamlType>ist, nachdem der erforderliche <xref:System.Xaml.XamlType> XAML-Schemakontext und der Dienst, den <xref:System.Windows.Markup.IXamlTypeResolver> der Kontext bereitstellt, nachuntersucht wurde.

In .NET XAML Services wird die Verarbeitung für <xref:System.Windows.Markup.TypeExtension> diese Markuperweiterung durch die Klasse definiert.

In bestimmten Frameworkimplementierungen können <xref:System.Type> einige Eigenschaften, die als Wert annehmen, den Namen `Name`des Typs direkt akzeptieren (den Zeichenfolgenwert des Typs ). Die Implementierung dieses Verhaltens ist jedoch ein komplexes Szenario. Beispiele finden Sie im folgenden Abschnitt "WPF-Verwendungshinweise".

Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Type`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.TypeExtension.TypeName%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.TypeExtension>-Erweiterungsklasse zugeordnet. Unter dem Standardmäßigen XAML-Schemakontext für .NET XAML Services, der auf CLR-Typen basiert, ist der Wert dieses Attributs entweder der <xref:System.Reflection.MemberInfo.Name%2A> des gewünschten Typs oder enthält das <xref:System.Reflection.MemberInfo.Name%2A> Präfix für eine nicht standardmäßige XAML-Namespacezuordnung.

Die `x:Type` Markuperweiterung kann in der Objektelementsyntax verwendet werden. In diesem Fall ist die <xref:System.Windows.Markup.TypeExtension.TypeName%2A> Angabe des Werts der Eigenschaft erforderlich, um die Erweiterung ordnungsgemäß zu initialisieren.

Die `x:Type` Markuperweiterung kann auch als ausführliches Attribut verwendet werden. Diese Verwendung ist jedoch nicht typisch:`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

### <a name="default-xaml-namespace-and-type-mapping"></a>Standard-XAML-Namespace und Typzuordnung

Der standardmäßige XAML-Namespace für die WPF-Programmierung enthält die meisten XAML-Typen, die Sie für typische XAML-Szenarien benötigen. Daher können Sie häufig Präfixe vermeiden, wenn Sie auf XAML-Typwerte verweisen. Möglicherweise müssen Sie ein Präfix zuordnen, wenn Sie auf einen Typ aus einer benutzerdefinierten Assembly oder auf Typen verweisen, die in einer WPF-Assembly vorhanden sind, aber aus einem CLR-Namespace stammen, der nicht dem standardmäßigen XAML-Namespace zugeordnet wurde. Weitere Informationen zu Präfixen, XAML-Namespaces und Zuordnung von CLR-Namespaces finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

### <a name="type-properties-that-support-typename-as-string"></a>Typeigenschaften, die Typename-as-String unterstützen

WPF unterstützt Techniken, die die Angabe des <xref:System.Type> Werts `x:Type` einiger Eigenschaften des Typs ermöglichen, ohne dass eine Markuperweiterungsverwendung erforderlich ist. Stattdessen können Sie den Wert als Zeichenfolge angeben, die den Typ benennt. Beispiele hierfür <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>sind und . Unterstützung für dieses Verhalten wird weder durch Typkonverter noch über Markuperweiterungen bereitgestellt. Stattdessen handelt es sich um ein <xref:System.Windows.FrameworkElementFactory>Aufschubverhalten, das über implementiert wird.

Silverlight unterstützt eine ähnliche Konvention. Tatsächlich unterstützt `{x:Type}` Silverlight derzeit keine XAML-Sprachunterstützung und akzeptiert `{x:Type}` keine Verwendungen außerhalb einiger Umstände, die die WPF-Silverlight XAML-Migration unterstützen sollen. Daher ist das Typname-as-String-Verhalten in allen Silverlight-Eigenschaftenauswertungen integriert, bei denen a <xref:System.Type> der Wert ist.

## <a name="xaml-2009"></a>XAML 2009

XAML 2009 bietet zusätzliche Unterstützung für generische Typen `x:TypeArguments` und `x:Type` ändert das Feature-Verhalten von und bietet diese Unterstützung.

- `x:TypeArguments`und das zugeordnete Objektelement für eine generische Objektinstanziierung kann sich auf anderen Elementen als dem Stamm befinden. Weitere Informationen finden Sie im Abschnitt "XAML 2009" der [x:TypeArguments-Richtlinie](xtypearguments-directive.md).

- XAML 2009 unterstützt eine Syntax zum Angeben der Einschränkung eines generischen Typs in Markup. Dies kann `x:TypeArguments`von `x:Type`verwendet werden, von , oder von den beiden Features in Kombination.

- Die WPF XAML-Implementierung bei der Verarbeitung von XAML 2009 für die Auslastung <xref:System.Type>fügt diese Funktion auch dem impliziten Typkonvertierungsverhalten für bestimmte Frameworkeigenschaften hinzu, die vom Typ verwenden.

In WPF können Sie XAML 2009-Features verwenden, jedoch nur für loses XAML (XAML, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Style>
- [Erstellen von Formaten und Vorlagen](../fundamentals/styles-templates-overview.md)
- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
