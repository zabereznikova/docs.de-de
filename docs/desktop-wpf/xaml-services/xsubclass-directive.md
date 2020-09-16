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
ms.openlocfilehash: b888ef73d1678fd37c984e4bb223f24e5b65d2cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540718"
---
# <a name="xsubclass-directive"></a>x:Subclass-Anweisung

Ändert das XAML-Markup Kompilierungs Verhalten, wenn `x:Class` ebenfalls bereitgestellt wird. Anstatt eine partielle Klasse zu erstellen, die auf basiert `x:Class` , wird der bereitgestellte `x:Class` als Zwischenklasse erstellt, und die bereitgestellte abgeleitete Klasse wird erwartet, dass auf basiert `x:Class` .

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`namespace`|Dies ist optional. Gibt einen CLR-Namespace an, der enthält `classname` . Wenn `namespace` angegeben wird, werden von einem Punkt (.) `namespace` und getrennt `classname` .|
|`classname`|Erforderlich. Gibt den CLR-Namen der partiellen Klasse an, die die geladene XAML und den Code Behind für dieses XAML verbindet. Siehe Hinweise.|
|`subclassNamespace`|Dies ist optional. Kann sich von unterscheiden, `namespace` Wenn jeder Namespace die andere auflösen kann. Gibt einen CLR-Namespace an, der enthält `subclassName` . Wenn `subclassName` angegeben wird, werden von einem Punkt (.) `subclassNamespace` und getrennt `subclassName` .|
|`subclassName`|Erforderlich. Gibt den CLR-Namen der Unterklasse an.|

## <a name="dependencies"></a>Abhängigkeiten

die [x:Class-Direktive](xclass-directive.md) muss auch für dasselbe Objekt bereitgestellt werden, und dieses Objekt muss das Stamm Element der XAML-Produktion sein.

## <a name="remarks"></a>Hinweise

`x:Subclass` die Verwendung ist hauptsächlich für Sprachen gedacht, die keine partiellen Klassen Deklarationen unterstützen.

Die als verwendete Klasse `x:Subclass` kann keine als eine Klasse der Klasse "-Klasse" sein und `x:Subclass` muss auf das Stamm Objekt verweisen, wie im Abschnitt "Abhängigkeiten" erläutert.

Andernfalls wird die konzeptionelle Bedeutung von `x:Subclass` durch eine .net-XAML-Dienst Implementierung nicht definiert. Dies liegt daran, dass das .net XAML-Dienst Verhalten nicht das allgemeine Programmiermodell angibt, mit dem XAML-Markup und Unterstützungs Code verbunden sind. Implementierungen weiterer Konzepte im Zusammenhang mit `x:Class` und `x:Subclass` werden von bestimmten Frameworks durchgeführt, die Programmier Modelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML-Markup, kompiliertes Markup und CLR-basiertes Code Behind verbunden werden. Jedes Framework kann über eigene Buildaktionen verfügen, die ein Teil des Verhaltens oder bestimmte Komponenten ermöglichen, die in der Buildumgebung enthalten sein müssen. Innerhalb eines Frameworks können Buildaktionen auch abhängig von der spezifischen CLR-Sprache variieren, die für den Code-Behind verwendet wird.

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

`x:Subclass` kann sich in einem Seiten Stamm oder im Stammverzeichnis <xref:System.Windows.Application> der Anwendungs Definition befinden, die bereits über verfügt `x:Class` . `x:Subclass`Wenn Sie in einem anderen Element als einer Seite oder einem Anwendungs Stamm deklarieren, oder wenn es nicht `x:Class` vorhanden ist, wird ein Kompilierzeitfehler verursacht.

Das Erstellen abgeleiteter Klassen, die für das Szenario ordnungsgemäß funktionieren, `x:Subclass` ist ziemlich komplex. Möglicherweise müssen Sie die zwischen Dateien (die. g-Dateien, die im Ordner "obj" des Projekts erstellt wurden, durch Markup Kompilierung untersuchen, wobei die Namen der XAML-Dateinamen enthalten). Diese zwischen Dateien können Ihnen helfen, den Ursprung bestimmter Programmierungskonstrukte in den in der kompilierten Anwendung eingefügten partiellen Klassen zu bestimmen.

Ereignishandler in der abgeleiteten Klasse müssen `internal override` ( `Friend Overrides` in Microsoft Visual Basic) sein, um die Stubel für die Handler zu überschreiben, die während der Kompilierung in der Zwischenklasse erstellt wurden. Andernfalls blenden die abgeleiteten Klassen Implementierungen die Implementierung der Zwischenklasse aus (Schatten), und die zwischen Klassen Handler werden nicht aufgerufen.

Wenn Sie sowohl als `x:Class` auch definieren `x:Subclass` , müssen Sie keine Implementierung für die Klasse bereitstellen, auf die von verwiesen wird `x:Class` . Sie müssen dem Attribut lediglich einen Namen über das- `x:Class` Attribut zuweisen, damit der Compiler über eine Anleitung für die Klasse verfügt, die in den zwischen Dateien erstellt wird (in diesem Fall wählt der Compiler keinen Standardnamen aus). Sie können der `x:Class` -Klasse eine-Implementierung übergeben. Dies ist jedoch nicht das typische Szenario für die Verwendung von `x:Class` und `x:Subclass` .

## <a name="see-also"></a>Siehe auch

- [x:Class-Direktive](xclass-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
