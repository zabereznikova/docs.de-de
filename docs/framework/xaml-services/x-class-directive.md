---
title: "x:Class Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:Class"
  - "xClass"
  - "Class"
helpviewer_keywords: 
  - "Class attribute in XAML [XAML Services]"
  - "XAML [XAML Services], x:Class attribute"
  - "x:Class attribute [XAML Services]"
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 26
---
# x:Class Directive
Konfiguriert die XAML\-Markupkompilierung so, dass partielle Klassen zwischen Markup und CodeBehind verknüpft werden.  Die partielle Klasse im Code wird in einer [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]\-Sprache als separate Codedatei definiert, während die partielle Klasse im Markup meist während der XAML\-Kompilierung vom Code\-Generator erstellt wird.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`namespace`|Optional.  Gibt einen [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)]\-Namespace an, der die mithilfe von `classname` identifizierte partielle Klasse enthält.  Wenn `namespace` angegeben ist, werden `namespace` und `classname` durch einen Punkt \(.\) getrennt.  Siehe Hinweise.|  
|`classname`|Erforderlich.  Gibt den [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)]\-Namen der partiellen Klasse an, die den geladenen XAML\-Code und den Code\-Behind für XAML verbindet.|  
  
## Abhängigkeiten  
 `x:Class` kann nur auf dem Stammelement einer XAML\-Produktion angegeben werden.  `x:Class` ist auf jedem Objekt ungültig, das über ein übergeordnetes Element in der XAML\-Produktion verfügt.  Weitere Informationen finden Sie unter [b\[MS\-XAML\] Abschnitt 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Hinweise  
 Der  `namespace`\-Wert enthält möglicherweise zusätzliche Punkte, um verwandte Namespaces in Namenshierarchien zu organisieren, was ein übliches Verfahren in der .NET Framework\-Programmierung ist.  Nur der letzte Punkt in einer Zeichenfolge für `x:Class`\-Werte wird interpretiert, um `namespace` und `classname.` zu trennen. Die als `x:Class` verwendete Klasse darf keine geschachtelte Klasse sein.  Geschachtelte Klassen sind nicht zugelassen, da die Bestimmung der Bedeutungen von Punkten für `x:Class`\-Zeichenfolgen mehrdeutig wäre, wenn geschachtelte Klassen erlaubt würden.  
  
 In vorhandenen Programmiermodellen, die `x:Class` verwenden, ist `x:Class` optional, da es vollkommen gültig ist, dass eine XAML\-Seite ohne CodeBehind vorhanden ist.  Diese Fähigkeit interagiert jedoch mit den von Frameworks implementierten Buildvorgängen, die XAML verwenden.  `x:Class`\-Funktion wird auch von den Rollen beeinflusst, die verschiedene Klassifizierungen von XAML\-Inhalt in einem Anwendungsmodell und in den entsprechenden Buildvorgängen haben.  Wenn die XAML Ereignisbehandlungsattributwerte deklariert oder benutzerdefinierte Elemente instanziiert, bei denen die definierenden Klassen sich in der Code\-Behind\-Klasse befinden, müssen Sie den `x:Class`\-Direktivenverweis \(oder [x:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)\) für die entsprechende Klasse für Code\-Behind bereitstellen.  
  
 Der Wert der `x:Class`\-Direktive muss eine Zeichenfolge sein, die den vollqualifizierten Namen einer Klasse angibt, jedoch ohne Assemblyinformationen \(Entsprechung zu <xref:System.Type.FullName%2A?displayProperty=fullName>\).  Bei einfachen Anwendungen können Sie CLR\-Namespaceinformationen weglassen, solange der Code\-Behind entsprechend strukturiert ist \(die Codedefinition beginnt auf Klassenebene\).  
  
 Die Code\-Behind\-Datei für eine Seiten\- oder Anwendungsdefinition muss sich innerhalb einer Codedatei befinden, die als Teil des Projekts eingefügt wird, das eine kompilierte Anwendung erstellt und eine Markupkompilierung involviert.  Für CLR\-Klassen müssen Namensregeln beachtet werden.  Weitere Informationen finden Sie unter [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md).  Standardmäßig muss die Code\-Behind\-Klasse `public` sein. Allerdings können Sie sie auf einer anderen Zugriffsebene definieren, indem Sie [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) verwenden.  
  
 Die Interpretation des `x:Class`\-Attributs gilt nur für eine CLR\-basierte XAML\-Implementierung, insbesondere für .NET Framework\-XAML\-Dienste.  Andere XAML\-Implementierungen, die nicht auf CLR basieren und keine .NET Framework XAML\-Dienste verwenden, könnten eine andere Auflösungsformel zum Verbinden von XAML\-Markup und Unterstützen von Laufzeitcode verwenden.  Weitere Informationen zu allgemeineren Auslegungen von `x:Class` finden Sie in der [\[MS\-XAML\]\-Sprachspezifikation](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 Auf einer bestimmten Ebene der Architektur ist die Bedeutung von `x:Class` in .NET Framework XAML\-Diensten nicht definiert.  Das liegt daran, dass die XAML\-Dienste von .NET Framework das Gesamtprogrammiermodell nicht angeben, durch das XAML\-Markup und der unterstützende Code verbunden sind.  Weitere `x:Class`\-Direktivenverwendungen können von bestimmten Frameworks implementiert werden, die Programmiermodelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML\-Markup und CLR\-basiertes Code\-Behind verbunden werden.  Jedes Framework kann eigene Buildvorgänge haben, die einen Teil des Verhaltens aktivieren, oder bestimmte Komponenten, die in der Buildumgebung enthalten sein müssen.  Innerhalb eines Frameworks können Buildvorgänge auch von der bestimmten Programmiersprache CLR abhängen, die für das Code\-Behind verwendet wird.  
  
## x:Class im WPF\-Programmiermodell  
 In WPF\-Anwendungen und dem WPF\-Anwendungsmodell kann `x:Class` als Attribut für jedes Element deklariert werden, das der Stamm einer XAML\-Datei ist und kompiliert wird \(wobei das XAML in einem WPF\-Anwendungsprojekt mit dem `Page`\-Buildvorgang enthalten ist\), oder für den <xref:System.Windows.Application>\-Stamm in der Anwendungsdefinition einer kompilierten WPF\-Anwendung.  Das Deklarieren von `x:Class` für ein Element, bei dem es sich nicht um einen Seitenstamm oder Anwendungsstamm handelt, oder für eine nicht kompilierte WPF\-XAML\-Datei führt zu einem Fehler zur Kompilierzeit unter dem [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]\- und [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)]\-WPF\-XAML\-Compiler.  Informationen zu anderen Aspekten der `x:Class`\-Behandlung in WPF finden Sie unter [Code\-Behind und XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## x:Class für Windows Workflow Foundation  
 Für Windows Workflow Foundation benennt `x:Class` die Klasse einer vollständig in XAML erstellten benutzerdefinierten Aktivität oder die partielle Klasse der XAML\-Seite für einen Aktivitäts\-Designer mit Code\-Behind.  
  
## Silverlight\-Verwendungshinweise  
 `x:Class` für Silverlight wird separat dokumentiert.  Weitere Informationen finden Sie unter [Sprachfeatures des XAML\-Namespace \(x:\)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## Siehe auch  
 [x:Subclass Directive](../../../docs/framework/xaml-services/x-subclass-directive.md)   
 [XAML\- und benutzerdefinierte Klassen für WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)