---
title: x:Subclass-Anweisung
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: e85e0fb5a0e1a865ed84a93767f8152a115bbe5f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432641"
---
# <a name="xsubclass-directive"></a>x:Subclass-Anweisung

Ändert das XAML-Markupkompilierungsverhalten, wenn `x:Class` es ebenfalls bereitgestellt wird. Anstatt eine partielle Klasse `x:Class`zu erstellen, die auf basiert, wird die bereitgestellte `x:Class` als Zwischenklasse erstellt, und dann wird erwartet, dass die bereitgestellte abgeleitete Klasse auf `x:Class`basiert.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`namespace`|Optional. Gibt einen CLR-Namespace `classname`an, der enthält. Wenn `namespace` angegeben, trennt ein Punkt `namespace` (.) und `classname`.|
|`classname`|Erforderlich. Gibt den CLR-Namen der partiellen Klasse an, die das geladene XAML und ihren CodeBehind für diese XAML verbindet. Siehe Hinweise.|
|`subclassNamespace`|Optional. Kann anders `namespace` sein, als wenn jeder Namespace den anderen auflösen kann. Gibt einen CLR-Namespace `subclassName`an, der enthält. Wenn `subclassName` angegeben, trennt ein Punkt `subclassNamespace` (.) und `subclassName`.|
|`subclassName`|Erforderlich. Gibt den CLR-Namen der Unterklasse an.|

## <a name="dependencies"></a>Abhängigkeiten

[x:Klassenrichtlinie](xclass-directive.md) muss auch für dasselbe Objekt bereitgestellt werden, und dieses Objekt muss das Stammelement der XAML-Produktion sein.

## <a name="remarks"></a>Bemerkungen

`x:Subclass`Verwendung ist in erster Linie für Sprachen gedacht, die keine partiellen Klassendeklarationen unterstützen.

Die Klasse, `x:Subclass` die als die verwendet `x:Subclass` wird, kann keine geschachtelte Klasse sein und muss sich auf das Stammobjekt beziehen, wie im Abschnitt "Abhängigkeiten" erläutert.

Andernfalls wird die `x:Subclass` konzeptionelle Bedeutung von nicht durch eine .NET XAML Services-Implementierung definiert. Dies liegt daran, dass das Verhalten von .NET XAML Services nicht das allgemeine Programmiermodell angibt, mit dem XAML-Markup und Sicherungscode verbunden sind. Implementierungen weiterer Konzepte `x:Class` im `x:Subclass` Zusammenhang mit und werden von bestimmten Frameworks durchgeführt, die Programmiermodelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML-Markup, kompiliertes Markup und CLR-basiertes CodeBehind verbunden werden. Jedes Framework verfügt möglicherweise über eigene Buildaktionen, die einige des Verhaltens oder bestimmte Komponenten aktivieren, die in der Buildumgebung enthalten sein müssen. Innerhalb eines Frameworks können Buildaktionen auch basierend auf der spezifischen CLR-Sprache variieren, die für den CodeBehind verwendet wird.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

`x:Subclass`kann sich auf einem Seitenstamm oder auf dem <xref:System.Windows.Application> Stamm `x:Class`in der Anwendungsdefinition befinden, die bereits über . Das `x:Subclass` Deklarieren eines anderen Elements als einer Seite oder `x:Class` eines Anwendungsstamms oder dessen Angabe, wenn kein Element vorhanden ist, verursacht einen Kompilierungsfehler.

Das Erstellen abgeleiteter Klassen, `x:Subclass` die für das Szenario ordnungsgemäß funktionieren, ist ziemlich komplex. Möglicherweise müssen Sie die Zwischendateien untersuchen (die .g-Dateien, die im obj-Ordner Ihres Projekts durch Markupkompilierung mit Namen erstellt wurden, die die .xaml-Dateinamen enthalten). Diese Zwischendateien können Ihnen helfen, den Ursprung bestimmter Programmierkonstrukte in den verbundenen Teilklassen in der kompilierten Anwendung zu bestimmen.

Ereignishandler in der abgeleiteten `internal override` `Friend Overrides` Klasse müssen (in Microsoft Visual Basic) sein, um die Stubs für die Handler zu überschreiben, wie sie in der Zwischenklasse während der Kompilierung erstellt wurden. Andernfalls werden in den abgeleiteten Klassenimplementierungen (Schatten) die Implementierung der Zwischenklasse ausgeblendet, und die Zwischenklassenhandler werden nicht aufgerufen.

Wenn Sie `x:Class` sowohl `x:Subclass`als auch definieren, müssen Sie keine Implementierung für `x:Class`die Klasse bereitstellen, auf die von verwiesen wird. Sie müssen ihm nur einen `x:Class` Namen über das Attribut geben, damit der Compiler einige Anleitungen für die Klasse hat, die er in den Zwischendateien erstellt (der Compiler wählt in diesem Fall keinen Standardnamen aus). Sie können `x:Class` der Klasse eine Implementierung geben. Dies ist jedoch nicht das `x:Class` typische `x:Subclass`Szenario für die Verwendung von beiden und .

## <a name="see-also"></a>Weitere Informationen

- [x:Class-Direktive](xclass-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
