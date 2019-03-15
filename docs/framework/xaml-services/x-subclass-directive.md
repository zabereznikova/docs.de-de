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
ms.openlocfilehash: c348d8fa2bd66a9abbb64c9363bb4dae0933ba34
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58048000"
---
# <a name="xsubclass-directive"></a>x:Subclass-Anweisung
Ändert die XAML-Markup kompilieren Verhalten beim `x:Class` wird ebenfalls bereitgestellt. Statt eine partielle Klasse, die basierend auf `x:Class`, bereitgestellten `x:Class` wird erstellt, wie ein intermediate-Klasse, und klicken Sie dann Ihre bereitgestellte abgeleitete Klasse wird erwartet, dass auf basiert `x:Class`.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`namespace`|Dies ist optional. Gibt einen CLR-Namespace, die enthält `classname`. Wenn `namespace` angegeben ist, einen Punkt (.) getrennt `namespace` und `classname`.|  
|`classname`|Erforderlich. Gibt den CLR-Namen der partiellen Klasse, die die geladene XAML und der Code-Behind für diese XAML verbindet. Siehe Hinweise.|  
|`subclassNamespace`|Dies ist optional. Von unterscheiden können `namespace` Wenn jeden Namespace auf den anderen auflösen kann. Gibt einen CLR-Namespace, die enthält `subclassName`. Wenn `subclassName` angegeben ist, einen Punkt (.) getrennt `subclassNamespace` und `subclassName`.|  
|`subclassName`|Erforderlich. Gibt den CLR-Namen der Unterklasse.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 [X: Class-Anweisung](x-class-directive.md) muss auch auf das gleiche Objekt bereitgestellt werden und das Objekt muss das Stammelement der XAML-Produktion.  
  
## <a name="remarks"></a>Hinweise  
 `x:Subclass` Nutzung dient in erster Linie für Sprachen, die Deklarationen der partiellen Klasse nicht unterstützen.  
  
 Die Klasse als die `x:Subclass` nicht geschachtelte Klassen und `x:Subclass` muss auf das Stammobjekt verweisen, wie im Abschnitt "Dependencies" erläutert.  
  
 Andernfalls die konzeptionelle Bedeutung von `x:Subclass` ist nicht definiert, durch eine Implementierung von .NET Framework-XAML-Dienste. Dies ist, da .NET Framework-XAML-Dienste Verhalten nicht das allgemeine Programmiermodell angibt, durch die, das XAML-Markup und Code sichern verbunden sind. Implementierungen von weiteren Konzepte im Zusammenhang mit `x:Class` und `x:Subclass` von bestimmten Frameworks, mit denen Programmiermodelle oder Anwendungsmodelle definieren, wie XAML-Markup, das kompilierte Markup und Code-Behind-CLR-basierte Verbindung ausgeführt werden. Jedes Framework möglicherweise eigene Buildvorgänge, die es ermöglichen, einige der das Verhalten oder die bestimmte Komponenten, die in der Buildumgebung enthalten sein müssen. In einem Framework können-Build Actions auch basierend auf bestimmten CLR-Sprache variieren, die für das Code-Behind verwendet wird.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 `x:Subclass` kann sein, oder auf eine Seitenstamm der <xref:System.Windows.Application> Stamm in die Definition der Anwendung, die bereits hat `x:Class`. Deklarieren von `x:Subclass` auf ein beliebiges Element als eine Seite oder Anwendung Stamm oder wenn keine Angabe `x:Class` vorhanden ist, verursacht einen Fehler während der Kompilierung.  
  
 Erstellen von abgeleiteten Klassen, die ordnungsgemäß für funktionieren die `x:Subclass` Szenario ist relativ komplex. Sie müssen möglicherweise untersuchen die Zwischendateien (g von erzeugten Dateien im Ordner "Obj" des Projekts Markupkompilierung, mit dem Namen, die die XAML-Dateien enthalten). Diese temporären Dateien können Sie das Ermitteln des Ursprungs bestimmter Konstrukte in der verknüpften partiellen Klassen in der kompilierten Anwendung.  
  
 Ereignishandler in der abgeleiteten Klasse muss `internal override` (`Friend Overrides` in Microsoft Visual Basic) um die Stubs für die Handler zu überschreiben, wie in der Zwischenklasse während der Kompilierung erstellt. Andernfalls die Implementierungen der abgeleiteten Klasse ausblenden (Schattenkopien) der Implementierung dazwischen liegende Klasse und die fortgeschrittene Klassenhandler werden nicht aufgerufen.  
  
 Wenn Sie beide definieren `x:Class` und `x:Subclass`, Sie müssen keine Implementierung für die Klasse angeben, die verweist `x:Class`. Sie müssen nur diese über benennen die `x:Class` Attribut, damit der Compiler verfügt über einige Hinweise für die Klasse, die es in die Zwischendateien erstellt (der Compiler ist nicht wählen Sie einen Standardnamen in diesem Fall). Sie erhalten die `x:Class` Klasse eine Implementierung; Dies ist jedoch nicht das typische Szenario für die Verwendung beider `x:Class` und `x:Subclass`.  
  
## <a name="see-also"></a>Siehe auch
- [x:Class-Anweisung](x-class-directive.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
