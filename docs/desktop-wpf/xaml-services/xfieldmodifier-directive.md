---
title: x:FieldModifier-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3e104b4c464d545e048f29901701c1c3dbb68229
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432779"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier-Anweisung
Ändert das XAML-Kompilierungsverhalten, sodass <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Felder für <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> benannte Objektverweise mit Zugriff anstelle des Standardverhaltens definiert werden.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|*Öffentlich*|Die genaue Zeichenfolge, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Sie angeben, hängt von der verwendeten Programmiersprache codebehind ab. Siehe Hinweise.|

## <a name="dependencies"></a>Abhängigkeiten

 Wenn eine XAML-Produktion an einer beliebigen Stelle verwendet wird, `x:FieldModifier` muss das Stammelement dieser XAML-Produktion eine [x:Class-Direktive](xclass-directive.md)deklarieren.

## <a name="remarks"></a>Bemerkungen

`x:FieldModifier`ist für die Deklaration der allgemeinen Zugriffsebene einer Klasse oder ihrer Member nicht relevant. Sie ist nur für das XAML-Verarbeitungsverhalten relevant, wenn ein bestimmtes XAML-Objekt, das Teil einer XAML-Produktion ist, verarbeitet wird und zu einem Objekt wird, auf das möglicherweise im Objektdiagramm einer Anwendung zugegriffen werden kann. Standardmäßig wird der Feldverweis für ein solches Objekt privat gehalten, wodurch Kontrollbenutzer daran gehindert werden, das Objektdiagramm direkt zu ändern. Stattdessen wird von Steuerelement-Verbrauchern erwartet, dass sie das Objektdiagramm mithilfe von Standardmustern ändern, die durch Programmiermodelle aktiviert werden, z. B. durch Abrufen des Layoutstamms, der untergeordneten Elementauflistungen, der dedizierten öffentlichen Eigenschaften usw.

Der Wert `x:FieldModifier` für das Attribut variiert je nach Programmiersprache, und sein Zweck kann in bestimmten Frameworks variieren. Die zu verwendende Zeichenfolge hängt davon <xref:System.CodeDom.Compiler.CodeDomProvider> ab, wie jede Sprache ihre und <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>die Typkonverter implementiert, die sie zurückgibt, um die Bedeutungen für und zu definieren, und ob die Groß-/Kleinschreibung dieser Sprache berücksichtigt wird.

- Die Zeichenfolge, die übergeben werden <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public`soll, ist für C.

- Für Microsoft Visual Basic .NET lautet <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public`die Zeichenfolge, die übergeben werden soll, um sie festzulegen, .

- Für C++/CLI sind derzeit keine Ziele für XAML vorhanden. Daher ist die zu übergebende Zeichenfolge nicht definiert.

Sie können <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> auch`internal` angeben (in C- und `Friend` <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Visual Basic), aber die Angabe ist ungewöhnlich, da `NotPublic` das Verhalten bereits die Standardeinstellung ist.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>ist das Standardverhalten, da es selten ist, dass Code außerhalb der Assembly, die das XAML kompiliert hat, Zugriff auf ein von XAML erstelltes Element benötigt. Die WPF-Sicherheitsarchitektur und das XAML-Kompilierungsverhalten deklarieren keine `x:FieldModifier` Felder, die Elementinstanzen als öffentlich speichern, es sei denn, Sie legen die so fest, dass der öffentliche Zugriff zulässt.

`x:FieldModifier`ist nur für Elemente mit einer [x:Name-Richtlinie](xname-directive.md) relevant, da dieser Name verwendet wird, um auf das Feld zu verweisen, nachdem es öffentlich ist.

Standardmäßig ist die partielle Klasse für das Root-Element öffentlich. Sie können es jedoch nicht öffentlich machen, indem Sie die [x:ClassModifier-Richtlinie](xclassmodifier-directive.md)verwenden. Die [x:ClassModifier-Direktive](xclassmodifier-directive.md) wirkt sich auch auf die Zugriffsebene der Instanz der root-Elementklasse aus. Sie können `x:Name` sowohl `x:FieldModifier` und auf dem Stammelement setzen, aber dies macht nur eine öffentliche Feldkopie des Root-Elements, wobei die true root-Element-Klassenzugriffsebene weiterhin durch [die x:ClassModifier-Direktive](xclassmodifier-directive.md)gesteuert wird.

## <a name="see-also"></a>Weitere Informationen

- [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Code-Behind und XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name-Anweisung](xname-directive.md)
- [Erstellen einer WPF-Anwendung (WPF)](../../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [x:ClassModifier-Anweisung](xclassmodifier-directive.md)
