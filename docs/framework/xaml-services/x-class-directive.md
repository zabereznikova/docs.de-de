---
title: x:Class-Anweisung
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
ms.openlocfilehash: 7e6a2379640d2556b553d14d20398a0a14931393
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566807"
---
# <a name="xclass-directive"></a>x:Class-Anweisung
Konfiguriert die Verwendung von XAML-Markupkompilierung partielle Klassen zwischen Markup und CodeBehind verknüpft. Die partielle Klasse im Code wird in einer separaten Codedatei im definiert eine [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] Sprache, während die partielle Klasse im Markup in der Regel durch die Generierung von Code während der Verwendung von XAML-Kompilierung erstellt wird.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`namespace`|Dies ist optional. Gibt eine [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] Namespace, die partielle Klasse identifizierte enthält `classname`. Wenn `namespace` angegeben ist, wird ein Punkt (.) trennt `namespace` und `classname`. Siehe Hinweise.|  
|`classname`|Erforderlich. Gibt die [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] Name der partiellen Klasse, die die geladene XAML und der Code-Behind für XAML verbindet.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 `x:Class` kann nur für das Stammelement einer XAML-Produktion angegeben werden. `x:Class` für jedes Objekt, das ein übergeordnetes Element, in der XAML-Produktion verfügt ist ungültig. Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Hinweise  
 Die `namespace` Wert enthält möglicherweise zusätzliche Punkte zum Organisieren von verwandten Namespaces in Namenshierarchien, dies ist ein gängiges Verfahren in .NET Framework-Programmierung. Nur der letzte Punkt in einer Zeichenfolge `x:Class` Werte interpretiert separaten `namespace` und `classname.` die Klasse, die verwendet wird, als `x:Class` nicht mit eine geschachtelte Klasse. Geschachtelte Klassen sind nicht zulässig, da die Bedeutung der Punkte für die Bestimmung `x:Class` Zeichenfolgen ist mehrdeutig, wenn geschachtelte Klassen zulässig sind.  
  
 Programmieren Sie Modelle, die in vorhandenen `x:Class`, `x:Class` ist optional, in dem Sinne, dass er eine XAML-Seite vorhanden sein, das keine Code-Behind wurde vollständig gültig ist. Diese Funktion interagiert jedoch die Buildvorgänge wie von Frameworks implementiert, die XAML verwenden. `x:Class` Funktion wird auch durch die Rollen beeinflusst, verschiedenen Klassifizierungen des angegebenen XAML-Inhalt in einem Anwendungsmodell haben, und erstellen in den entsprechenden Aktionen. Wenn XAML-Code deklariert Ereignisbehandlung Attribut Werte oder benutzerdefinierte Elemente, in denen die definierenden Klassen in der Code-Behind-Klasse sind, instanziiert, müssen Sie angeben der `x:Class` Richtlinie Verweis (oder [X: Subclass-](../../../docs/framework/xaml-services/x-subclass-directive.md)) auf der geeignet für Code-Behind-Klasse.  
  
 Der Wert von der `x:Class` Richtlinie muss eine Zeichenfolge, die den vollqualifizierten Namen einer Klasse, aber ohne Assemblyinformationen gibt an (entspricht der <xref:System.Type.FullName%2A?displayProperty=nameWithType>). Einfache Anwendungen können Sie CLR-Namespaceinformationen weglassen, wenn der Code-Behind auch auf diese Weise (Code Definition beginnt auf Klassenebene) strukturiert ist.  
  
 Der Code-Behind-Datei für die Definition einer Seite oder Anwendung muss innerhalb einer Codedatei, die als Teil des Projekts enthalten ist, die eine kompilierte Anwendung erstellt und umfasst die Markupkompilierung enthalten ist. Sie müssen den Regeln für CLR-Klassen einhalten. Weitere Informationen finden Sie unter [Framework-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md). Standardmäßig muss der Code-Behind-Klasse `public`, aber Sie können es an eine andere Zugriffsebene definieren, mit der [X: ClassModifier-Direktive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
 Die Interpretation der der `x:Class` Attribut gilt nur für eine CLR-basierten XAML-Implementierung, insbesondere für .NET Framework-XAML-Dienste. Andere XAML-Implementierungen, die nicht auf CLR basieren und ohne .NET Framework-XAML-Dienste verwenden, möglicherweise eine andere Lösung Formel für die Verbindung von XAML-Markup und Sichern von Code zur Laufzeit verwenden. Weitere Informationen zu allgemeinen Interpretationen von `x:Class`, finden Sie unter [ \[MS-XAML-\]](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 Auf einer bestimmten Ebene der Architektur, die Bedeutung der `x:Class` ist nicht in .NET Framework XAML Services definiert. Dies ist, da .NET Framework-XAML-Dienste nicht das Programmiermodell angibt, durch das XAML-Markup und Code sichern verbunden sind. Zusätzliche Verwendungen von der `x:Class` Richtlinie implementiert werden könnten, von bestimmten Frameworks, die Programmiermodelle oder Anwendungsmodelle verwenden, um XAML-Markup und CodeBehind CLR-basierten Herstellen einer Verbindung zu definieren. Jedes Framework kann eine eigene Buildvorgänge haben, mit denen einige der das Verhalten oder die bestimmte Komponenten, die in der Buildumgebung enthalten sein müssen. In einem Framework können Buildvorgänge auch abhängig von der bestimmten CLR-Sprache variieren, die für das Code-Behind-Modell verwendet wird.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>X: Class in WPF-Programmiermodell  
 In WPF-Anwendungen und das WPF-Anwendungsmodell `x:Class` kann als ein Attribut deklariert werden, für jedes Element, ist der Stamm einer XAML-Datei und kompiliert wird (bei denen der XAML-Code enthalten ist, in einem WPF-Anwendungsprojekt mit `Page` Buildvorgang), oder für die < C4 > <xref:System.Windows.Application>  Stamm in der Anwendungsdefinition kompilierte WPF-Anwendung. Deklarieren von `x:Class` auf ein Element als Stammelement einer Seite oder Anwendungsstamm, oder eine WPF XAML-Datei, die nicht kompiliert wird, verursacht einen Fehler während der Kompilierung unter der [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] und [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] WPF XAML-Compiler. Informationen zu anderen Aspekten der `x:Class` Behandlung in WPF finden Sie unter [Code-Behind-XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## <a name="xclass-for-windows-workflow-foundation"></a>X: Class für Windows Workflow Foundation  
 Für Windows Workflow Foundation `x:Class` benennt die Klasse von einer benutzerdefinierten Aktivität, die vollständig in XAML oder den Namen der partiellen Klasse der XAML-Seite für einen Aktivitäts-Designer mit CodeBehind.  
  
## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise  
 `x:Class` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace ("x:") Sprachfunktionen (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Siehe auch  
 [x:Subclass-Anweisung](../../../docs/framework/xaml-services/x-subclass-directive.md)  
 [XAML- und benutzerdefinierte Klassen für WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [x:ClassModifier-Anweisung](../../../docs/framework/xaml-services/x-classmodifier-directive.md)  
 [Aus WPF zu System.Xaml migrierte Typen](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
