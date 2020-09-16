---
title: x:ClassModifier-Anweisung
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 73732a06029cca3a4c6c6d82762d5263c5b8c955
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544816"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier-Anweisung
Ändert das XAML-Kompilierungs Verhalten, wenn `x:Class` ebenfalls bereitgestellt wird. Anstatt eine partielle zu erstellen, die `class` über eine `Public` Zugriffsebene (Standardeinstellung) verfügt, wird der bereitgestellte `x:Class` mit einer `NotPublic` Zugriffsebene erstellt. Dieses Verhalten wirkt sich auf die Zugriffsebene für die-Klasse in den generierten Assemblys aus.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|*NotPublic*|Die genaue Zeichenfolge, die an <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> übergeben <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> werden soll, und variiert abhängig von der verwendeten Programmiersprache Code-Behind. Siehe Hinweise.|

## <a name="dependencies"></a>Abhängigkeiten

[x:Class](xclass-directive.md) muss auch für dasselbe Element bereitgestellt werden, und dieses Element muss das Stamm Element in einer Seite sein. Weitere Informationen finden Sie im [ \[ Abschnitt zu MS-XAML \] 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Hinweise

Der Wert von `x:ClassModifier` in der .net XAML-Dienste-Verwendung variiert je nach Programmiersprache. Die zu verwendende Zeichenfolge hängt davon ab, wie die jeweilige Sprache implementiert <xref:System.CodeDom.Compiler.CodeDomProvider> , und die Typkonverter, die zurückgegeben werden, um die Bedeutung für und zu definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>

- Für c# ist die Zeichenfolge, die an übergeben werden soll, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal` .

- Bei Microsoft Visual Basic .net ist die Zeichenfolge, die an übergeben werden soll, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend` .

- Für C++/CLI sind keine Ziele vorhanden, die das Kompilieren von XAML unterstützen. Daher ist der zu Übergabe Wert nicht angegeben.

Sie können auch <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` in c# `Public` in Visual Basic) angeben. die Angabe von <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist jedoch nur selten durchgeführt, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> bereits das Standardverhalten ist.

Andere Werte mit äquivalenten Zugriffs ebeneneinschränkungen für Benutzercode, wie z. b. `private` in c#, sind für nicht relevant, `x:ClassModifier` da in XAML keine Klassen Verweise unterstützt werden und der- <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Modifizierer daher dieselbe Auswirkung hat.

## <a name="security-notes"></a>Sicherheitshinweise

Die Zugriffsebene, wie Sie in deklariert `x:ClassModifier` wird, unterliegt weiterhin der Interpretation durch bestimmte Frameworks und deren Funktionen. WPF enthält Funktionen zum Laden und Instanziieren von Typen `x:ClassModifier` , bei denen ist `internal` , wenn auf diese Klasse von einer WPF-Ressource über einen Paket-URI-Verweis verwiesen wird. In diesem Fall und möglicherweise andere, wie Sie von anderen Frameworks implementiert werden, verlassen sich nicht ausschließlich darauf, dass `x:ClassModifier` alle möglichen instanziierungsversuche blockiert werden.

## <a name="see-also"></a>Siehe auch

- [x:Class-Direktive](xclass-directive.md)
- [Code-Behind und XAML in WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [x:FieldModifier-Anweisung](xfieldmodifier-directive.md)
- [Sicherheit (WPF)](/dotnet/desktop/wpf/security-wpf)
- [Aus WPF zu System.Xaml migrierte Typen](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
