---
title: x:FieldModifier-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 4e67a6dac49b8d6a7d316526f99a1519b08fd68b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554474"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier-Anweisung
Ändert das XAML-Kompilierungs Verhalten, sodass Felder für benannte Objekt Verweise mit <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Access anstelle des <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Standard Verhaltens definiert werden.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|*Öffentlich*|Die genaue Zeichenfolge, die Sie an übergeben, wenn Sie angeben <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , oder variiert, hängt von der verwendeten Code-Behind-Programmiersprache ab. Siehe Hinweise.|

## <a name="dependencies"></a>Abhängigkeiten

 Wenn eine XAML-Produktion einen `x:FieldModifier` beliebigen Speicherort verwendet, muss das Stamm Element dieser XAML-Produktion eine [x:Class-Direktive](xclass-directive.md)deklarieren.

## <a name="remarks"></a>Hinweise

`x:FieldModifier` ist für das Deklarieren der allgemeinen Zugriffsebene einer Klasse oder ihrer Member nicht relevant. Sie ist nur für das XAML-Verarbeitungs Verhalten relevant, wenn ein bestimmtes XAML-Objekt, das Teil einer XAML-Produktion ist, verarbeitet wird, und wird zu einem Objekt, auf das im Objekt Diagramm einer Anwendung möglicherweise zugegriffen werden kann. Standardmäßig wird der Feldverweis für ein solches Objekt als privat gespeichert, wodurch verhindert wird, dass Steuerungs Consumer das Objekt Diagramm direkt ändern können. Stattdessen wird erwartet, dass Steuerungs Consumer das Objekt Diagramm mithilfe von Standard Mustern ändern, die von Programmier Modellen aktiviert werden, z. b. durch Abrufen des Layoutstamms, der untergeordneten Element Auflistungen, der dedizierten öffentlichen Eigenschaften usw.

Der Wert des `x:FieldModifier` -Attributs variiert je nach Programmiersprache, und sein Zweck kann sich in bestimmten Frameworks unterscheiden. Die zu verwendende Zeichenfolge hängt davon ab, wie die jeweilige Sprache implementiert <xref:System.CodeDom.Compiler.CodeDomProvider> , und die Typkonverter, die zurückgegeben werden, um die Bedeutung für und zu definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>

- Für c# ist die Zeichenfolge, die an übergeben werden soll, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public` .

- Bei Microsoft Visual Basic .net ist die Zeichenfolge, die an übergeben werden soll, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public` .

- Für C++/CLI sind zurzeit keine Ziele für XAML vorhanden. Daher ist die zu über gebende Zeichenfolge nicht definiert.

Sie können auch <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ( `internal` in c# `Friend` in Visual Basic) angeben. die Angabe von ist jedoch ungewöhnlich, da <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `NotPublic` das Verhalten bereits der Standard ist.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist das Standardverhalten, da es selten auftritt, dass Code außerhalb der Assembly, die den XAML-Code kompiliert hat, Zugriff auf ein XAML-erstelltes Element benötigt. Die WPF-Sicherheitsarchitektur und das XAML-Kompilierungs Verhalten deklarieren keine Felder, die Element Instanzen als öffentlich speichern, es sei denn, Sie legen ausdrücklich fest, `x:FieldModifier` um öffentlichen Zugriff zuzulassen.

`x:FieldModifier` ist nur für Elemente mit einer [x:Name-Direktive](xname-directive.md) relevant, da dieser Name verwendet wird, um auf das Feld zu verweisen, nachdem es öffentlich ist.

Standardmäßig ist die partielle Klasse für das Stamm Element öffentlich. Sie können Sie jedoch nicht öffentlich machen, indem Sie die [x:ClassModifier-Direktive](xclassmodifier-directive.md)verwenden. Die [x:ClassModifier-Direktive](xclassmodifier-directive.md) wirkt sich auch auf die Zugriffsebene der Instanz der Stamm Element Klasse aus. Sie können sowohl `x:Name` als auch `x:FieldModifier` für das root-Element platzieren, aber dadurch wird nur eine öffentliche Feld Kopie des Stamm Elements erstellt, wobei die Zugriffsebene der echten Stamm Element Klasse weiterhin durch die [x:ClassModifier-Direktive](xclassmodifier-directive.md)gesteuert wird.

## <a name="see-also"></a>Siehe auch

- [XAML- und benutzerdefinierte Klassen für WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
- [Code-Behind und XAML in WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [x:Name-Anweisung](xname-directive.md)
- [Entwickeln einer WPF-Anwendung (WPF)](/dotnet/desktop/wpf/app-development/building-a-wpf-application-wpf)
- [x:ClassModifier-Anweisung](xclassmodifier-directive.md)
