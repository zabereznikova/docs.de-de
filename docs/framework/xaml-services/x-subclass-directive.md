---
title: "x:Subclass Directive | Microsoft Docs"
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
  - "Subclass"
  - "xSubclass"
  - "x:Subclass"
helpviewer_keywords: 
  - "x:Subclass attribute [XAML Services]"
  - "XAML [XAML Services], x:Subclass attribute"
  - "Subclass attribute in XAML [XAML Services]"
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Subclass Directive
Ändert das XAML\-Markupkompilierungsverhalten, wenn `x:Class` ebenfalls bereitgestellt wird.  Anstatt eine partielle Klasse basierend auf der `x:Class`\-Klasse zu erstellen, wird die angegebene `x:Class` als Zwischenklasse erstellt, und es wird dann erwartet, dass die von Ihnen bereitgestellte abgeleitete Klasse auf `x:Class` basiert.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`namespace`|Optional.  Gibt einen CLR\-Namespace an, der`classname` enthält.  Wenn `namespace` angegeben ist, werden `namespace` und `classname` durch einen Punkt \(.\) getrennt.|  
|`classname`|Erforderlich.  Gibt den CLR\-Namen der partiellen Klasse an, die den geladenen XAML\-Code und Ihren CodeBehind für das XAML verbindet.  Siehe Hinweise.|  
|`subclassNamespace`|Optional.  Kann sich von `namespace` unterscheiden, wenn ein Namespace den anderen auflösen kann.  Gibt einen CLR\-Namespace an, der`subclassName` enthält.  Wenn `subclassName` angegeben ist, werden `subclassNamespace` und `subclassName` durch einen Punkt \(.\) getrennt.|  
|`subclassName`|Erforderlich.  Gibt den CLR\-Namen der Unterklasse an.|  
  
## Abhängigkeiten  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) muss auch auf demselben Objekt bereitgestellt werden, und dieses Objekt muss das Stammelement der XAML\-Produktion sein.  
  
## Hinweise  
 Die Verwendung von `x:Subclass` ist hauptsächlich für Sprachen bestimmt, die keine Deklarationen für partielle Klassen unterstützen.  
  
 Die als `x:Subclass` verwendete Klasse kann keine geschachtelte Klasse sein, und `x:Subclass` muss auf das Stammobjekt verweisen, wie im Abschnitt "Abhängigkeiten" erklärt.  
  
 Andernfalls wird die konzeptionelle Bedeutung von `x:Subclass` von der Implementierung der .NET Framework\-XAML\-Dienste nicht definiert.  Das liegt daran, dass das Verhalten der .NET Framework XAML\-Dienste das Gesamtprogrammiermodell nicht angibt, durch das XAML\-Markup und der unterstützende Code verbunden sind.  Implementierungen weiterer Konzepte zu `x:Class` und `x:Subclass` wird von bestimmten Frameworks ausgeführt, die Programmiermodelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML\-Markup, kompiliertes Markup und CLR\-basiertes Code\-Behind verbunden werden.  Jedes Framework könnte eigene Buildvorgänge haben, die einen Teil des Verhaltens aktivieren, oder bestimmte Komponenten, die in der Buildumgebung enthalten sein müssen.  Innerhalb eines Frameworks können Buildvorgänge auch auf der bestimmten Programmiersprache CLR beruhen, die für das Code\-Behind verwendet wird.  
  
## Hinweise zur WPF\-Verwendung  
 `x:Subclass` kann ein Seite\-Stammelement oder ein <xref:System.Windows.Application>\-Stammelement in der Anwendungsdefinition sein, für die bereits `x:Class` definiert wurde.  Das Deklarieren von `x:Subclass` für alle Elemente, bei denen es sich nicht um das Stammelement einer Seite oder Anwendung handelt, oder das Angeben an Positionen, an denen `x:Class` nicht vorhanden ist, führt zu einem Kompilierzeitfehler.  
  
 Die Erstellung von abgeleiteten Klassen, die für das `x:Subclass`\-Szenario richtig funktionieren, ist recht komplex.  Es kann sein, dass Sie die Zwischendateien untersuchen müssen \(die G\-Dateien, die im Ordner "obj" Ihres Projekts mit Markupkompilierung erstellt werden, die die Namen der XAML\-Dateien enthalten\).  Diese Zwischendateien unterstützen Sie beim Bestimmen des Ursprungs bestimmter Konstrukte in den verknüpften partiellen Klassen innerhalb der kompilierten Anwendung.  
  
 Ereignishandler in der abgeleiteten Klasse müssen den Typ `internal override` aufweisen \(`Friend Overrides` in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]\), um die Stubs für die Handler zu überschreiben, die während der Kompilierung in der Zwischenklasse erstellt wurden.  Andernfalls werden die Implementierungen der abgeleiteten Klasse die Implementierung der Zwischenklasse ausblenden \(Shadowing\), und die Zwischenklassenhandler könnten nicht aufgerufen werden.  
  
 Wenn Sie sowohl `x:Class` als auch `x:Subclass` definieren, müssen Sie keine Implementierung für die Klasse angeben, auf die über `x:Class` verwiesen wird.  Sie müssen nur einen Namen über das `x:Class`\-Attribut angeben, damit der Compiler über Anweisungen zur Klasse verfügt, die in den Zwischendateien erstellt wird \(der Compiler wählt in diesem Fall keinen Standardnamen aus\).  Sie können der `x:Class`\-Klasse eine Implementierung ermöglichen. Dies ist jedoch nicht als typisches Szenario für die Verwendung von `x:Class` und `x:Subclass` empfohlen.  
  
## Siehe auch  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [XAML\- und benutzerdefinierte Klassen für WPF](../../../ocs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)