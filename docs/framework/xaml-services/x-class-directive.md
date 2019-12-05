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
ms.openlocfilehash: d6baa6d8eb3a6d3520fb1549e2182f27ca52c36a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837245"
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
|`namespace`|Dies ist optional. Gibt einen CLR-Namespace an, der die durch `classname`identifizierte partielle Klasse enthält. Wenn `namespace` angegeben wird, trennt ein Punkt (.) `namespace` und `classname`. Siehe Hinweise.|  
|`classname`|Erforderlich Gibt den CLR-Namen der partiellen Klasse an, die die geladene XAML und den Code Behind für dieses XAML verbindet.|  
  
## <a name="dependencies"></a>-Abhängigkeiten  
 `x:Class` können nur für das Stamm Element einer XAML-Produktion angegeben werden. `x:Class` für ein Objekt, das über ein übergeordnetes Element in der XAML-Produktion verfügt, ist ungültig. Weitere Informationen finden Sie unter [\[MS-XAML\] Abschnitt 4.3.1.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="remarks"></a>Hinweise  
 Der `namespace`-Wert kann zusätzliche Punkte enthalten, um verwandte Namespaces in namens Hierarchien zu organisieren. Dies ist eine gängige Technik bei .NET Framework Programmierung. Nur der letzte Punkt in einer Zeichenfolge mit `x:Class` Werten wird so interpretiert, dass `namespace` getrennt werden, und `classname.` die Klasse, die als `x:Class` verwendet wird, nicht als eine-Klasse verwendet werden kann. Es sind keine untergeordneten Klassen zulässig, da die Bestimmung der Bedeutung von Punkten für `x:Class` Zeichen folgen mehrdeutig ist, wenn die zulässigen Klassen zulässig sind.  
  
 In vorhandenen Programmier Modellen, die `x:Class`verwenden, ist `x:Class` optional, dass es vollständig gültig ist, eine XAML-Seite ohne Code Behind zu haben. Diese Funktion interagiert jedoch mit den Build-Aktionen, die von Frameworks implementiert werden, die XAML verwenden. `x:Class` Funktion wird auch von den Rollen beeinflusst, die verschiedene Klassifizierungen von XAML-spezifiziertem Inhalt in einem Anwendungsmodell und in den entsprechenden Buildaktionen aufweisen. Wenn Ihr XAML-Attributwerte für die Ereignis Behandlung deklariert oder benutzerdefinierte Elemente instanziiert, in denen sich die definierenden Klassen in der Code-Behind-Klasse befinden, müssen Sie den `x:Class` direktivenverweis (oder [x:Subclass](x-subclass-directive.md)) der entsprechenden Klasse für Code Behind bereitstellen.  
  
 Der Wert der `x:Class`-Direktive muss eine Zeichenfolge sein, die den voll qualifizierten Namen einer Klasse, aber ohne Assemblyinformationen (äquivalent zum <xref:System.Type.FullName%2A?displayProperty=nameWithType>) angibt. Bei einfachen Anwendungen können Sie CLR-Namespace Informationen weglassen, wenn der Code-Behind auch auf diese Weise strukturiert ist (die Code Definition beginnt auf Klassenebene).  
  
 Die Code-Behind-Datei für eine Seiten-oder Anwendungs Definition muss sich in einer Codedatei befinden, die als Teil des Projekts enthalten ist, das eine kompilierte Anwendung erstellt und eine Markup Kompilierung umfasst. Sie müssen den namens Regeln für CLR-Klassen folgen. Weitere Informationen finden Sie unter [Framework-Entwurfs Richtlinien](../../standard/design-guidelines/index.md). Standardmäßig muss die Code-Behind-Klasse `public`werden. Sie können es jedoch mithilfe der [x:ClassModifier-Direktive](x-classmodifier-directive.md)auf einer anderen Zugriffsebene definieren.  
  
 Diese Interpretation des `x:Class` Attributs gilt nur für eine CLR-basierte XAML-Implementierung, insbesondere für .NET Framework XAML-Dienste. Andere XAML-Implementierungen, die nicht auf CLR basieren und keine .NET Framework XAML-Dienste verwenden, verwenden möglicherweise eine andere Auflösungs Formel zum Verbinden von XAML-Markup und zum unterstützen von Lauf Zeit Code. Weitere Informationen zu allgemeineren Interpretationen von `x:Class`finden Sie unter [\[MS-XAML-\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
 In einer bestimmten Architekturebene ist die Bedeutung von `x:Class` in .NET Framework XAML-Diensten nicht definiert. Dies liegt daran, dass .NET Framework XAML-Dienste nicht das Programmiermodell angibt, mit dem XAML-Markup und Unterstützungs Code verbunden sind. Zusätzliche Verwendungen der `x:Class`-Direktive können von bestimmten Frameworks implementiert werden, die Programmier Modelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML-Markup und CLR-basiertes Code Behind miteinander verbunden werden. Jedes Framework kann über eigene Buildaktionen verfügen, die ein Teil des Verhaltens oder bestimmte Komponenten ermöglichen, die in der Buildumgebung enthalten sein müssen. Innerhalb eines Frameworks können Buildaktionen auch abhängig von der spezifischen CLR-Sprache variieren, die für den Code-Behind verwendet wird.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>x:Class im WPF-Programmiermodell  
 In WPF-Anwendungen und im WPF-Anwendungsmodell können `x:Class` als Attribut für jedes Element deklariert werden, das das Stamm Element einer XAML-Datei ist und kompiliert wird (wobei der XAML-Code in einem WPF-Anwendungsprojekt mit `Page` Buildaktion enthalten ist), oder für den <xref:System.Windows.Application> Stamm in der Anwendungs Definition einer kompilierten WPF-Anwendung. Das Deklarieren von `x:Class` auf einem anderen Element als einem Seiten Stamm-oder Anwendungs Stamm oder in einer nicht kompilierten WPF-XAML-Datei verursacht einen Kompilierzeitfehler unter dem .NET Framework 3,0 und .NET Framework 3,5 WPF-XAML-Compiler. Weitere Informationen zu anderen Aspekten der `x:Class` Behandlung in WPF finden Sie unter [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>x:Class für Windows Workflow Foundation  
 Für Windows Workflow Foundation benennt `x:Class` die Klasse einer benutzerdefinierten Aktivität, die vollständig in XAML verfasst ist, oder benennt die partielle Klasse der XAML-Seite für einen Aktivitäts Designer mit Code Behind.  
  
## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise  
 `x:Class` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace (x:). Sprach Features (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Siehe auch

- [x:Subclass-Anweisung](x-subclass-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier-Anweisung](x-classmodifier-directive.md)
- [Aus WPF zu System.Xaml migrierte Typen](types-migrated-from-wpf-to-system-xaml.md)
