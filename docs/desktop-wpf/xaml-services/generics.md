---
title: Generics in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432959"
---
# <a name="generics-in-xaml"></a>Generics in XAML

.NET XAML Services, <xref:System.Xaml?displayProperty=fullName> wie in implementiert, bietet Unterstützung für die Verwendung generischer CLR-Typen. Diese Unterstützung umfasst das Angeben der Einschränkungen von Generika als Typargument `Add` und das Erzwingen der Einschränkung durch Aufrufen der geeigneten Methode für generische Auflistungsfälle. In diesem Thema werden Aspekte der Verwendung und Referenzierung generischer Typen in XAML beschrieben.

## <a name="xtypearguments"></a>x:TypeArgumente

`x:TypeArguments`ist eine Direktive, die durch die XAML-Sprache definiert wird. Wenn er als Member eines XAML-Typs verwendet wird, `x:TypeArguments` der von einem generischen Typ unterstützt wird, werden einschränkende Typargumente des generischen Elements an den Sicherungskonstruktor übergibt. Referenzsyntax, die sich auf die Verwendung von `x:TypeArguments`.NET XAML Services bezieht, die Syntaxbeispiele enthält, finden Sie unter [x:TypeArguments-Direktive](xtypearguments-directive.md).

Da `x:TypeArguments` eine Zeichenfolge verwendet wird und Typkonverterunterstützt ist, wird sie in der Regel in der XAML-Verwendung als Attribut deklariert.

Im XAML-Knotenstream können die `x:TypeArguments` von deklarierten Informationen an <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> einer `StartObject` Position im Knotenstream abgerufen werden. Der Rückgabewert <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> von ist <xref:System.Xaml.XamlType> eine Liste von Werten. Bestimmen, ob ein XAML-Typ einen generischen <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>Typ darstellt, kann durch Aufrufen von vorgenommen werden.

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Regeln und Syntaxkonventionen für Generika in XAML

In XAML muss ein generischer Typ immer als eingeschränktes generisches Element dargestellt werden. Ein nicht eingeschränktes generisches Element ist nie im XAML-Typsystem oder in einem XAML-Knotenstream vorhanden und kann nicht im XAML-Markup dargestellt werden. Ein generisches Element kann innerhalb der XAML-Attributsyntax für Fälle referenziert werden, `x:TypeArguments`in denen `x:Type` es sich um eine geschachtelte Typeinschränkung eines generischen Typs handelt, auf das von verwiesen wird, oder für Fälle, in denen eine CLR-Typreferenz für einen generischen Typ bereitstellt. Das Verweisen auf Generika <xref:System.Xaml.Schema.XamlTypeTypeConverter> wird über die von .NET XAML Services definierte Klasse unterstützt.

Das XAML-Attributsyntaxformular, das durch <xref:System.Xaml.Schema.XamlTypeTypeConverter> aktivieren wird, ändert die typische MSIL/CLR-Syntaxkonvention, die spitze Klammern für Typen und Einschränkungen von Generika verwendet und stattdessen Klammern für den Einschränkungscontainer ersetzt. Ein Beispiel finden Sie unter [x:TypeArguments-Direktive](xtypearguments-directive.md).

## <a name="generics-and-xaml-2009-features"></a>Generisches und XAML 2009-Funktionen

Wenn Sie XAML 2009 verwenden, anstatt die CLR-Basistypen zuzuordnen, um XAML-Typen für primitive Benutzerfürsweiterungen `x:TypeArguments`in gängiger Sprache zu erhalten, können Sie [integrierte XAML 2009-Typen](types-for-primitives.md) als Informationselemente in verwenden. Sie können z. B. Folgendes deklarieren (Präfixzuordnungen werden nicht angezeigt, ist aber `x` der XAML-XAML-Namespace für XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>Generics Support in WPF

Für die XAML 2006-Verwendung bei spezieller Ausrichtung auf WPF `x:TypeArguments`muss [x:Class](xclass-directive.md) auch für dasselbe Element wie bereitgestellt werden, und dieses Element muss das Stammelement in einem XAML-Dokument sein. Das Root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden. z. B. <xref:System.Windows.Navigation.PageFunction%601>.

Mögliche Problemumgehungen zur Unterstützung generischer Verwendungen umfassen das Definieren einer benutzerdefinierten Markuperweiterung, die generische Typen zurückgeben kann, oder das Bereitstellen einer Wrapping-Klassendefinition, die von einem generischen Typ ableitet, aber die generische Einschränkung in ihrer eigenen Klassendefinition flacht.

In WPF können Sie XAML 2009-Features zusammen mit `x:TypeArguments`verwenden, jedoch nur für loses XAML (XAML, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.

Benutzerdefinierte Workflows in Windows Workflow Foundation für .NET Framework 3.5 unterstützen keine generische XAML-Nutzung.

## <a name="see-also"></a>Weitere Informationen

- [x:TypeArguments-Anweisung](xtypearguments-directive.md)
- [x:Class-Direktive](xclass-directive.md)
- [Integrierte Typen für häufige XAML-Sprachprimitive](types-for-primitives.md)
