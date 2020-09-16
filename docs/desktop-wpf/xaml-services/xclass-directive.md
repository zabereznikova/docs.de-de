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
ms.openlocfilehash: 8f7ca5fdb170411aba24d34b8bf4d6c4f5776cc4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555145"
---
# <a name="xclass-directive"></a>x:Class-Direktive
Konfiguriert die XAML-Markup Kompilierung so, dass partielle Klassen zwischen Markup und Code Behind verknüpft werden. Die partielle Code Klasse wird in einer separaten Codedatei in einer Common Language Specification (CLS)-Sprache definiert, wohingegen die partielle Markup Klasse bei der XAML-Kompilierung normalerweise von der Codegenerierung erstellt wird.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`namespace`|Dies ist optional. Gibt einen CLR-Namespace an, der die durch identifizierte partielle Klasse enthält `classname` . Wenn `namespace` angegeben wird, werden von einem Punkt (.) `namespace` und getrennt `classname` . Siehe Hinweise.|
|`classname`|Erforderlich. Gibt den CLR-Namen der partiellen Klasse an, die die geladene XAML und den Code Behind für dieses XAML verbindet.|

## <a name="dependencies"></a>Abhängigkeiten

`x:Class` kann nur für das Stamm Element einer XAML-Produktion angegeben werden. `x:Class` ist für ein Objekt, das über ein übergeordnetes Element in der XAML-Produktion verfügt, ungültig. Weitere Informationen finden Sie im [ \[ Abschnitt zu MS-XAML \] 4.3.1.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Hinweise

Der `namespace` Wert kann zusätzliche Punkte enthalten, um verwandte Namespaces in namens Hierarchien zu organisieren. Dies ist eine gängige Methode in der .NET-Programmierung. Nur der letzte Punkt in einer Zeichenfolge von `x:Class` Werten wird als getrennt interpretiert, `namespace` und `classname.` die Klasse, die als verwendet wird, `x:Class` kann keine untergeordnete Klasse sein. Es sind keine untergeordneten Klassen zulässig, da die Bestimmung der Bedeutung von Punkten für Zeichen folgen `x:Class` mehrdeutig ist, wenn die zulässigen Klassen zulässig sind.

In vorhandenen Programmier Modellen, die verwenden `x:Class` , `x:Class` ist in dem Sinne optional, dass eine XAML-Seite ohne Code Behind vollständig gültig ist. Diese Funktion interagiert jedoch mit den Build-Aktionen, die von Frameworks implementiert werden, die XAML verwenden. `x:Class` die Funktion wird auch von den Rollen beeinflusst, die verschiedene Klassifizierungen von XAML-spezifiziertem Inhalt in einem Anwendungsmodell und in den entsprechenden Buildaktionen aufweisen. Wenn Ihr XAML-Attributwerte für die Ereignis Behandlung deklariert oder benutzerdefinierte Elemente instanziiert, in denen sich die definierenden Klassen in der Code-Behind-Klasse befinden, müssen Sie den `x:Class` direktivenverweis (oder [x:Subclass](xsubclass-directive.md)) der entsprechenden Klasse für Code Behind bereitstellen.

Der Wert der- `x:Class` Direktive muss eine Zeichenfolge sein, die den voll qualifizierten Namen einer Klasse, aber ohne Assemblyinformationen (entspricht <xref:System.Type.FullName%2A?displayProperty=nameWithType> ) angibt. Bei einfachen Anwendungen können Sie CLR-Namespace Informationen weglassen, wenn der Code-Behind auch auf diese Weise strukturiert ist (die Code Definition beginnt auf Klassenebene).

Die Code-Behind-Datei für eine Seiten-oder Anwendungs Definition muss sich in einer Codedatei befinden, die als Teil des Projekts enthalten ist, das eine kompilierte Anwendung erstellt und eine Markup Kompilierung umfasst. Sie müssen den namens Regeln für CLR-Klassen folgen. Weitere Informationen finden Sie unter [Framework-Entwurfs Richtlinien](../../../api/index.md). Standardmäßig muss die Code-Behind-Klasse lauten `public` . Sie können Sie jedoch auf einer anderen Zugriffsebene definieren, indem Sie die [x:ClassModifier-Direktive](xclassmodifier-directive.md)verwenden.

Diese Interpretation des- `x:Class` Attributs gilt nur für eine CLR-basierte XAML-Implementierung, insbesondere für .net XAML-Dienste. Andere XAML-Implementierungen, die nicht auf CLR basieren und keine .net XAML-Dienste verwenden, verwenden möglicherweise eine andere Auflösungs Formel zum Verbinden von XAML-Markup und zum unterstützen von Lauf Zeit Code. Weitere Informationen zu allgemeineren Interpretationen von finden Sie `x:Class` unter [ \[ MS-XAML \] ](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

Auf einer bestimmten Architekturebene ist die Bedeutung von `x:Class` in .net XAML-Diensten nicht definiert. Dies liegt daran, dass .net XAML-Dienste das Programmiermodell nicht angeben, mit dem XAML-Markup und Unterstützungs Code verbunden sind. Zusätzliche Verwendungsmöglichkeiten der- `x:Class` Direktive können von bestimmten Frameworks implementiert werden, die Programmier Modelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML-Markup und CLR-basiertes Code Behind miteinander verbunden werden. Jedes Framework kann über eigene Buildaktionen verfügen, die ein Teil des Verhaltens oder bestimmte Komponenten ermöglichen, die in der Buildumgebung enthalten sein müssen. Innerhalb eines Frameworks können Buildaktionen auch abhängig von der spezifischen CLR-Sprache variieren, die für den Code-Behind verwendet wird.

## <a name="xclass-in-the-wpf-programming-model"></a>x:Class im WPF-Programmiermodell

In WPF-Anwendungen und im WPF-Anwendungsmodell `x:Class` kann als Attribut für jedes Element deklariert werden, das das Stamm Element einer XAML-Datei ist und kompiliert wird (wobei XAML in einem WPF-Anwendungsprojekt mit Buildaktion enthalten ist `Page` ), oder für den Stamm <xref:System.Windows.Application> in der Anwendungs Definition einer kompilierten WPF-Anwendung. Das deklarieren `x:Class` von für ein anderes Element als ein Seiten Stamm-oder Anwendungs Stamm oder für eine nicht kompilierte WPF-XAML-Datei verursacht einen Kompilierzeitfehler unter dem .NET Framework 3,0 und .NET Framework 3,5 WPF-XAML-Compiler. Weitere Informationen zu anderen Aspekten der `x:Class` Handhabung von in WPF finden Sie unter [Code-Behind und XAML in WPF](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf).

## <a name="xclass-for-windows-workflow-foundation"></a>x:Class für Windows Workflow Foundation
Für Windows Workflow Foundation `x:Class` benennt die Klasse einer benutzerdefinierten Aktivität, die vollständig in XAML verfasst ist, oder benennt die partielle Klasse der XAML-Seite für einen Aktivitäts Designer mit Code Behind.

## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise

`x:Class` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace (x:). Sprach Features (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Siehe auch

- [x:Subclass-Anweisung](xsubclass-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
- [x:ClassModifier-Anweisung](xclassmodifier-directive.md)
- [Aus WPF zu System.Xaml migrierte Typen](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
