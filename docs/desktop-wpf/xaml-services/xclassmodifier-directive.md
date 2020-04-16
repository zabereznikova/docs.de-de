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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433271"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier-Anweisung
Ändert das XAML-Kompilierungsverhalten, wenn `x:Class` es ebenfalls bereitgestellt wird. Anstatt eine `class` Teilebene mit einer `Public` Zugriffsebene (Standardeinstellung) `x:Class` zu erstellen, wird die bereitgestellte Mitschrift mit einer `NotPublic` Zugriffsebene erstellt. Dieses Verhalten wirkt sich auf die Zugriffsebene für die Klasse in den generierten Assemblys aus.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|*NotPublic*|Die genaue Zeichenfolge, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> übergeben werden soll, um anzugeben, variiert je nach verwendeter Programmiersprache codebehind. Siehe Hinweise.|

## <a name="dependencies"></a>Abhängigkeiten

[x:Class](xclass-directive.md) muss auch für dasselbe Element bereitgestellt werden, und dieses Element muss das Stammelement auf einer Seite sein. Weitere Informationen finden Sie unter [ \[\] MS-XAML Abschnitt 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Bemerkungen

Der Wert `x:ClassModifier` der Verwendung von in .NET XAML Services variiert je nach Programmiersprache. Die zu verwendende Zeichenfolge hängt davon <xref:System.CodeDom.Compiler.CodeDomProvider> ab, wie jede Sprache ihre und <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>die Typkonverter implementiert, die sie zurückgibt, um die Bedeutungen für und zu definieren, und ob die Groß-/Kleinschreibung dieser Sprache berücksichtigt wird.

- Die Zeichenfolge, die übergeben werden <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`soll, ist für C.

- Für Microsoft Visual Basic .NET lautet <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`die Zeichenfolge, die übergeben werden soll, um sie festzulegen, .

- Für C++/CLI sind keine Ziele vorhanden, die das Kompilieren von XAML unterstützen. Daher ist der zu übergebende Wert nicht angegeben.

Sie können <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> auch`public` angeben ( `Public` in C-Code, in Visual Basic); Die Angabe <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> erfolgt jedoch selten, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> sie bereits das Standardverhalten ist.

Andere Werte mit entsprechenden Einschränkungen für Benutzercodezugriffsebene, z. `private` `x:ClassModifier` B. in C,sind nicht relevant, da geschachtelte Klassenverweise in XAML nicht unterstützt werden und der <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Modifikator daher denselben Effekt hat.

## <a name="security-notes"></a>Sicherheitshinweise

Die in `x:ClassModifier` angegebene Zugangsebene unterliegt nach wie vor der Auslegung durch bestimmte Rahmen und ihre Fähigkeiten. WPF enthält Funktionen zum Laden und `x:ClassModifier` Instanziieren von Typen, wobei , `internal`wenn auf diese Klasse von einer WPF-Ressource über einen Pack-URI-Verweis verwiesen wird. Als Folge dieses Falles und möglicherweise andere wie es von anderen `x:ClassModifier` Frameworks implementiert, verlassen Sie sich nicht ausschließlich auf alle möglichen Instanziierungsversuche zu blockieren.

## <a name="see-also"></a>Weitere Informationen

- [x:Class-Direktive](xclass-directive.md)
- [Code-Behind und XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier-Anweisung](xfieldmodifier-directive.md)
- [Sicherheit (WPF)](../../framework/wpf/security-wpf.md)
- [Aus WPF zu System.Xaml migrierte Typen](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
