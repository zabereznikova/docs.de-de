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
ms.openlocfilehash: f6f02998a7648693bd731d6b2afdfd4499abaa04
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053911"
---
# <a name="xsubclass-directive"></a>x:Subclass-Anweisung
Ändert das XAML-Markup Kompilierungs `x:Class` Verhalten, wenn ebenfalls bereitgestellt wird. Anstatt eine partielle Klasse zu erstellen, die auf `x:Class`basiert, wird `x:Class` der bereitgestellte als Zwischenklasse erstellt, und die bereitgestellte abgeleitete Klasse wird erwartet, dass `x:Class`auf basiert.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`namespace`|Optional. Gibt einen CLR-Namespace an `classname`, der enthält. Wenn `namespace` angegeben wird, werden von einem Punkt (. `namespace` ) `classname`und getrennt.|  
|`classname`|Erforderlich. Gibt den CLR-Namen der partiellen Klasse an, die die geladene XAML und den Code Behind für dieses XAML verbindet. Siehe Hinweise.|  
|`subclassNamespace`|Optional. Kann sich von `namespace` unterscheiden, wenn jeder Namespace die andere auflösen kann. Gibt einen CLR-Namespace an `subclassName`, der enthält. Wenn `subclassName` angegeben wird, werden von einem Punkt (. `subclassNamespace` ) `subclassName`und getrennt.|  
|`subclassName`|Erforderlich. Gibt den CLR-Namen der Unterklasse an.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 die [x:Class-Direktive](x-class-directive.md) muss auch für dasselbe Objekt bereitgestellt werden, und dieses Objekt muss das Stamm Element der XAML-Produktion sein.  
  
## <a name="remarks"></a>Hinweise  
 `x:Subclass`die Verwendung ist hauptsächlich für Sprachen gedacht, die keine partiellen Klassen Deklarationen unterstützen.  
  
 Die als `x:Subclass` verwendete Klasse kann keine als eine Klasse der Klasse "- `x:Subclass` Klasse" sein und muss auf das Stamm Objekt verweisen, wie im Abschnitt "Abhängigkeiten" erläutert.  
  
 Andernfalls wird die konzeptionelle Bedeutung von `x:Subclass` durch eine .NET Framework XAML-Dienst Implementierung nicht definiert. Dies liegt daran, dass .NET Framework XAML-Dienst Verhalten nicht das gesamte Programmiermodell angibt, mit dem XAML-Markup und Unterstützungs Code verbunden sind. Implementierungen weiterer Konzepte im Zusammenhang `x:Class` mit `x:Subclass` und werden von bestimmten Frameworks durchgeführt, die Programmier Modelle oder Anwendungsmodelle verwenden, um zu definieren, wie XAML-Markup, kompiliertes Markup und CLR-basiertes Code Behind verbunden werden. Jedes Framework kann über eigene Buildaktionen verfügen, die ein Teil des Verhaltens oder bestimmte Komponenten ermöglichen, die in der Buildumgebung enthalten sein müssen. Innerhalb eines Frameworks können Buildaktionen auch abhängig von der spezifischen CLR-Sprache variieren, die für den Code-Behind verwendet wird.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 `x:Subclass`kann sich in einem Seiten Stamm oder <xref:System.Windows.Application> im Stammverzeichnis der Anwendungs Definition befinden, die bereits über verfügt. `x:Class` Wenn `x:Subclass` Sie in einem anderen Element als einer Seite oder einem Anwendungs Stamm deklarieren, oder `x:Class` wenn es nicht vorhanden ist, wird ein Kompilierzeitfehler verursacht.  
  
 Das Erstellen abgeleiteter Klassen, die `x:Subclass` für das Szenario ordnungsgemäß funktionieren, ist ziemlich komplex. Möglicherweise müssen Sie die zwischen Dateien (die. g-Dateien, die im Ordner "obj" des Projekts erstellt wurden, durch Markup Kompilierung untersuchen, wobei die Namen der XAML-Dateinamen enthalten). Diese zwischen Dateien können Ihnen helfen, den Ursprung bestimmter Programmierungskonstrukte in den in der kompilierten Anwendung eingefügten partiellen Klassen zu bestimmen.  
  
 Ereignishandler in der abgeleiteten Klasse müssen ( `internal override` `Friend Overrides` in Microsoft Visual Basic) sein, um die Stubel für die Handler zu überschreiben, die während der Kompilierung in der Zwischenklasse erstellt wurden. Andernfalls blenden die abgeleiteten Klassen Implementierungen die Implementierung der Zwischenklasse aus (Schatten), und die zwischen Klassen Handler werden nicht aufgerufen.  
  
 Wenn Sie sowohl `x:Class` als auch `x:Subclass`definieren, müssen Sie keine Implementierung für die Klasse bereitstellen, auf die von `x:Class`verwiesen wird. Sie müssen dem Attribut lediglich einen Namen über das `x:Class` -Attribut zuweisen, damit der Compiler über eine Anleitung für die Klasse verfügt, die in den zwischen Dateien erstellt wird (in diesem Fall wählt der Compiler keinen Standardnamen aus). Sie können der `x:Class` `x:Class` -Klasse eine-Implementierung übergeben. Dies ist jedoch nicht das typische Szenario für die Verwendung `x:Subclass`von und.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
