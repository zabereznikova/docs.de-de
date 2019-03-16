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
ms.openlocfilehash: 8acc1ac099a71fbf624049b119ebe908f27cbb55
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58031223"
---
# <a name="xclass-directive"></a>x:Class-Direktive
Konfiguriert die XAML-Markup-Kompilierung um partielle Klassen zwischen Markup und Code-Behind zu verknüpfen. Die partielle Klasse im Code wird in einer separaten Codedatei im definiert eine [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] Sprache, während die partielle Klasse im Markup durch Generierung von Code während der Kompilierung von XAML in der Regel erstellt wird.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`namespace`|Dies ist optional. Gibt an, eine [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] Namespace, der die partielle Klasse identifizierte enthält `classname`. Wenn `namespace` angegeben ist, einen Punkt (.) getrennt `namespace` und `classname`. Siehe Hinweise.|  
|`classname`|Erforderlich. Gibt an, die [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] Name der partiellen Klasse, die die geladene XAML und der Code-Behind für diese XAML verbunden werden.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 `x:Class` kann nur für das Stammelement einer XAML-Produktion angegeben werden. `x:Class` ist für jedes Objekt, das ein übergeordnetes Element in der XAML-Produktion ist ungültig. Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 4.3.1.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Hinweise  
 Die `namespace` Wert enthält möglicherweise zusätzliche Punkte zum Organisieren von verwandten Namespaces in Namenshierarchien, dies ist ein gängiges Verfahren in .NET Framework-Programmierung. Nur der letzte Punkt in einer Zeichenfolge `x:Class` Werte wird als separate interpretiert `namespace` und `classname.` die Klasse, die verwendet wird, als `x:Class` eine geschachtelte Klasse nicht möglich. Geschachtelte Klassen sind nicht zulässig, da die Bedeutung der Punkte für die Bestimmung `x:Class` Zeichenfolgen ist mehrdeutig, wenn geschachtelte Klassen zulässig sind.  
  
 In vorhandenen Programmiermodelle, mit denen `x:Class`, `x:Class` ist in dem Sinne, dass es vollständig gültig ist, wird eine XAML-Seite verwendet, die keine Code-Behind ist optional. Allerdings werden diese Fähigkeit mit den Buildvorgängen interagiert, wie von Frameworks implementiert wird, die XAML verwenden. `x:Class` Funktion wird durch die Rollen auch beeinflusst, dass die verschiedenen Klassifizierungen des angegebenen XAML-Inhalt in einem Anwendungsmodell haben, und erstellen in den entsprechenden Aktionen. Wenn Ihre XAML wird deklariert, zur Verarbeitung von Ereignissen Attribut Werte oder benutzerdefinierte Elemente, in denen die definierenden Klassen in der CodeBehind-Klasse sind, instanziiert, müssen Sie angeben der `x:Class` -Direktive Verweis (oder [X: Subclass-](x-subclass-directive.md)) auf der entsprechende Klasse für CodeBehind.  
  
 Der Wert des der `x:Class` Richtlinie muss eine Zeichenfolge, die den vollqualifizierten Namen einer Klasse, aber ohne Assemblyinformationen gibt an (entspricht der <xref:System.Type.FullName%2A?displayProperty=nameWithType>). Für einfache Anwendungen können Sie CLR-Namespaceinformationen weglassen, wenn das Code-Behind auch auf diese Weise (Code Definition beginnt auf der Klassenebene) strukturiert sind.  
  
 Der Code-Behind-Datei für die Definition einer Seite oder Anwendung muss innerhalb einer Codedatei, die als Teil des Projekts enthalten ist, die eine kompilierte Anwendung erstellt und umfasst die Markupkompilierung enthalten ist. Sie müssen den Regeln für CLR-Klassen befolgen. Weitere Informationen finden Sie unter [Framework-Entwurfsrichtlinien](../../standard/design-guidelines/index.md). Standardmäßig muss der Code-Behind-Klasse `public`, aber Sie können ihn an eine andere Zugriffsebene definieren, mit der [X: ClassModifier-Anweisung](x-classmodifier-directive.md).  
  
 Die Interpretation der der `x:Class` Attribut gilt nur für eine CLR-basierten XAML-Implementierung, insbesondere für .NET Framework-XAML-Dienste. Andere XAML-Implementierungen, die nicht auf CLR basieren und ohne .NET Framework-XAML-Dienste verwenden, können eine andere Lösung Formel für die Verbindung von XAML-Markup, und Sichern von Laufzeitcode verwenden. Weitere Informationen zu allgemeineren Interpretationen der `x:Class`, finden Sie unter [ \[MS-XAML-\]](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 Auf einer bestimmten Ebene der Architektur, die Bedeutung der `x:Class` ist nicht definiert. in .NET Framework-XAML-Dienste. Dies ist, da .NET Framework-XAML-Dienste nicht das Programmiermodell, das angibt, durch die, das XAML-Markup und Code sichern verbunden sind. Weitere Verwendungsmöglichkeiten des der `x:Class` Richtlinie implementiert werden könnte, von bestimmten Frameworks, mit denen Programmiermodelle oder Anwendungsmodelle XAML-Markup und Code-Behind-CLR-basierte Verbindung definieren. Jedes Framework haben einen eigenen Buildaktionen, mit denen einige der Verhalten oder bestimmte Komponenten, die in der Buildumgebung enthalten sein müssen. In einem Framework können-Build Actions auch abhängig von der bestimmten CLR-Sprache variieren, die für das Code-Behind verwendet wird.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>X: Class in das WPF-Programmiermodell  
 In WPF-Anwendungen und das WPF-Anwendungsmodell `x:Class` kann als Attribut deklariert werden, für jedes Element, ist der Stamm einer XAML-Datei und kompiliert wird (wo befindet sich der XAML in einem WPF-Anwendungsprojekt mit `Page` Buildvorgang), oder für die < C4 > <xref:System.Windows.Application>  Stamm in die Definition der Anwendung von einer kompilierten WPF-Anwendung. Deklarieren von `x:Class` für ein Element als Stammelement einer Seite oder Anwendungsstamm oder in einer WPF XAML-Datei, die nicht kompiliert wird, verursacht einen Fehler während der Kompilierung der [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] und [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] WPF XAML-Compiler. Informationen zu anderen Aspekte der `x:Class` in WPF behandeln, finden Sie unter [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>X: Class für Windows Workflow Foundation  
 Für Windows Workflow Foundation `x:Class` benennt die Klasse von einer benutzerdefinierten Aktivität vollständig in XAML oder Namen die partielle Klasse der XAML-Seite für einen Aktivitätsdesigner mit Code-Behind.  
  
## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise  
 `x:Class` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace (x:)) Sprachfunktionen (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Siehe auch
- [x:Subclass-Anweisung](x-subclass-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier-Anweisung](x-classmodifier-directive.md)
- [Aus WPF zu System.Xaml migrierte Typen](types-migrated-from-wpf-to-system-xaml.md)
