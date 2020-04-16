---
title: x:Class-Direktive
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: f589fa70c2ee1c56544fa0f0152990478aa3761f
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433277"
---
# <a name="xclass-directive"></a>x:Class-Direktive
Konfiguriert die XAML-Markupkompilierung so, dass teilklassige Klassen zwischen Markup und CodeBehind verknüpfungen. Die codepartielle Klasse wird in einer separaten Codedatei in einer CLS-Sprache (Common Language Specification) definiert, während die markuppartische Klasse in der Regel durch Codegenerierung während der XAML-Kompilierung erstellt wird.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`namespace`|Optional. Gibt einen CLR-Namespace an, der `classname`die partielle Klasse enthält, die durch identifiziert wurde. Wenn `namespace` angegeben, trennt ein Punkt `namespace` (.) und `classname`. Siehe Hinweise.|
|`classname`|Erforderlich. Gibt den CLR-Namen der partiellen Klasse an, die das geladene XAML und ihren CodeBehind für diese XAML verbindet.|

## <a name="dependencies"></a>Abhängigkeiten

`x:Class`kann nur für das Stammelement einer XAML-Produktion angegeben werden. `x:Class`ist für jedes Objekt ungültig, das ein übergeordnetes Objekt in der XAML-Produktion hat. Weitere Informationen finden Sie unter [ \[\] MS-XAML Abschnitt 4.3.1.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Bemerkungen

Der `namespace` Wert kann zusätzliche Punkte enthalten, um verknüpfte Namespaces in Namenshierarchien zu organisieren, was in der .NET-Programmierung eine gängige Methode ist. Nur der letzte Punkt `x:Class` in einer Zeichenfolge `namespace` `classname.` von Werten wird `x:Class` interpretiert, um zu trennen, und Die Klasse, die als verwendet wird, kann keine geschachtelte Klasse sein. Geschachtelte Klassen sind nicht zulässig, da `x:Class` das Bestimmen der Bedeutung von Punkten für Zeichenfolgen mehrdeutig ist, wenn geschachtelte Klassen zulässig sind.

In vorhandenen Programmiermodellen, `x:Class` die verwenden, `x:Class`ist dies in dem Sinne optional, dass es vollständig gültig ist, eine XAML-Seite zu haben, die keinen CodeBehind hat. Diese Funktion interagiert jedoch mit den Buildaktionen, die von Frameworks implementiert werden, die XAML verwenden. `x:Class`Die Funktion wird auch durch die Rollen beeinflusst, die verschiedene Klassifizierungen von XAML-spezifizierten Inhalten in einem Anwendungsmodell und in den entsprechenden Buildaktionen haben. Wenn Ihr XAML Attributwerte für die Ereignisbehandlung deklariert oder benutzerdefinierte Elemente instanziiert, bei denen `x:Class` sich die definierenden Klassen in der CodeBehind-Klasse befinden, müssen Sie den Direktivenverweis (oder [x:Subclass](xsubclass-directive.md)) für die entsprechende Klasse für code-behind bereitstellen.

Der Wert `x:Class` der Direktive muss eine Zeichenfolge sein, die den vollqualifizierten Namen einer <xref:System.Type.FullName%2A?displayProperty=nameWithType>Klasse angibt, jedoch keine Assemblyinformationen (entspricht der ). Bei einfachen Anwendungen können Sie CLR-Namespaceinformationen weglassen, wenn der CodeBehind ebenfalls auf diese Weise strukturiert ist (Codedefinition beginnt auf Klassenebene).

Die CodeBehind-Datei für eine Seiten- oder Anwendungsdefinition muss sich in einer Codedatei befinden, die als Teil des Projekts enthalten ist, das eine kompilierte Anwendung erstellt und eine Markupkompilierung umfasst. Sie müssen Namensregeln für CLR-Klassen befolgen. Weitere Informationen finden Sie unter [Framework Design Guidelines](../../../api/index.md). Standardmäßig muss die CodeBehind-Klasse `public`sein ; Sie können sie jedoch auf einer anderen Zugriffsebene definieren, indem Sie die [x:ClassModifier-Direktive verwenden.](xclassmodifier-directive.md)

Diese Interpretation `x:Class` des Attributs gilt nur für eine CLR-basierte XAML-Implementierung, insbesondere für .NET XAML Services. Andere XAML-Implementierungen, die nicht auf CLR basieren und keine .NET XAML-Dienste verwenden, verwenden möglicherweise eine andere Auflösungsformel zum Verbinden von XAML-Markup und zum Sichern von Laufzeitcode. Weitere Informationen zu allgemeineren `x:Class`Interpretationen von finden Sie unter [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

Auf einer bestimmten Architekturebene ist `x:Class` die Bedeutung von in .NET XAML Services nicht definiert. Dies liegt daran, dass .NET XAML Services nicht das Programmiermodell angibt, mit dem XAML-Markup und Sicherungscode verbunden sind. Zusätzliche Verwendungen `x:Class` der Direktive können von bestimmten Frameworks implementiert werden, die Programmiermodelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML-Markup und CLR-basierter CodeBehind verbunden werden. Jedes Framework kann über eigene Buildaktionen verfügen, die einige des Verhaltens oder bestimmte Komponenten aktivieren, die in der Buildumgebung enthalten sein müssen. Innerhalb eines Frameworks können Buildaktionen auch abhängig von der spezifischen CLR-Sprache variieren, die für den CodeBehind verwendet wird.

## <a name="xclass-in-the-wpf-programming-model"></a>x:Klasse im WPF-Programmiermodell

In WPF-Anwendungen und im `x:Class` WPF-Anwendungsmodell kann als Attribut für jedes Element deklariert werden, das der Stamm einer XAML-Datei ist `Page` und kompiliert <xref:System.Windows.Application> wird (wobei das XAML in einem WPF-Anwendungsprojekt mit Buildaktion enthalten ist) oder für den Stamm in der Anwendungsdefinition einer kompilierten WPF-Anwendung. Das `x:Class` Deklarieren eines anderen Elements als eines Seitenstamms oder Anwendungsstamms oder einer WPF XAML-Datei, die nicht kompiliert ist, verursacht einen Kompilierungsfehler unter .NET Framework 3.0 und .NET Framework 3.5 WPF XAML-Compiler. Weitere Informationen zu `x:Class` anderen Aspekten der Handhabung in WPF finden Sie unter [Code-Behind und XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

## <a name="xclass-for-windows-workflow-foundation"></a>x:Klasse für Windows Workflow Foundation
Benennt für `x:Class` Windows Workflow Foundation die Klasse einer benutzerdefinierten Aktivität, die vollständig in XAML zusammengesetzt ist, oder die Teilklasse der XAML-Seite für einen Aktivitäts-Designer mit CodeBehind.

## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise

`x:Class` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML Namespace (x:) Sprachfunktionen (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Weitere Informationen

- [x:Subclass-Anweisung](xsubclass-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier-Anweisung](xclassmodifier-directive.md)
- [Aus WPF zu System.Xaml migrierte Typen](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
