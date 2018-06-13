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
ms.openlocfilehash: b04982ff0b7685b4e4b809255e3bbe541b42cb9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566417"
---
# <a name="xsubclass-directive"></a>x:Subclass-Anweisung
Ändert die Verwendung von XAML-Markup kompilieren Verhalten beim `x:Class` ebenfalls bereitgestellt wird. Statt eine partielle Klasse, die basierend auf `x:Class`, bereitgestellten `x:Class` wird als eine Zwischenklasse erstellt und die angegebene abgeleitete Klasse wird dann auf der Grundlage erwartet `x:Class`.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`namespace`|Dies ist optional. Gibt einen CLR-Namespace, die enthält `classname`. Wenn `namespace` angegeben ist, wird ein Punkt (.) trennt `namespace` und `classname`.|  
|`classname`|Erforderlich. Gibt den CLR-Namen der partiellen Klasse, die die geladene XAML und der Code-Behind für XAML verbindet. Siehe Hinweise.|  
|`subclassNamespace`|Dies ist optional. Kann von anderen `namespace` Wenn jeden Namespace, die andere auflösen kann. Gibt einen CLR-Namespace, die enthält `subclassName`. Wenn `subclassName` angegeben ist, wird ein Punkt (.) trennt `subclassNamespace` und `subclassName`.|  
|`subclassName`|Erforderlich. Gibt den CLR-Namen der Unterklasse.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 [X: Class-Direktive](../../../docs/framework/xaml-services/x-class-directive.md) muss auch auf das gleiche Objekt angegeben werden, und dieses Objekt muss das Stammelement der XAML-Produktion.  
  
## <a name="remarks"></a>Hinweise  
 `x:Subclass` Verwendung dient in erster Linie für Sprachen, die partiellen Klassendeklarationen nicht unterstützen.  
  
 Die Klasse als verwendet die `x:Subclass` nicht mit eine geschachtelte Klasse und `x:Subclass` muss auf das Stammobjekt verweisen, wie im Abschnitt "Abhängigkeiten" erläutert.  
  
 Andernfalls die grundlegende Bedeutung der `x:Subclass` ist nicht definiert, durch eine .NET Framework-XAML-Dienste-Implementierung. Dies ist, da .NET Framework XAML Services-Verhalten nicht das gesamte Programmiermodell angibt, durch das XAML-Markup und Code sichern verbunden sind. Implementierungen von weiteren Konzepte im Zusammenhang mit `x:Class` und `x:Subclass` erfolgen durch spezifische Frameworks, die Programmiermodelle oder Anwendungsmodelle verwenden, um XAML-Markup, das kompilierte Markup und CodeBehind CLR-basierten Herstellen einer Verbindung zu definieren. Jedes Framework möglicherweise eigene Buildvorgänge, die es ermöglichen, einige der das Verhalten oder die bestimmte Komponenten, die in der Buildumgebung enthalten sein müssen. In einem Framework abhängig Buildvorgänge auch bestimmte CLR-Sprache, die für das Code-Behind-Modell verwendet wird.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 `x:Subclass` kann auf einer Seitenstamm oder die <xref:System.Windows.Application> Stamm in der Anwendungsdefinition, die bereits hat `x:Class`. Deklarieren von `x:Subclass` auf jedes Element außer einer Stamm-Seite oder einer Anwendung oder angegeben wird, denen keine `x:Class` vorhanden ist, verursacht einen Fehler zu Kompilierzeit.  
  
 Erstellen von abgeleiteten Klassen arbeitende ordnungsgemäß für die `x:Subclass` Szenario ist relativ komplex. Sie müssen möglicherweise die Zwischendateien (Zwischendateien erstellten Dateien im Ordner "Obj" des Projekts als Markup kompilieren, mit dem Namen, die die Namen der XAML-Dateien enthalten) untersuchen. Diese temporären Dateien können Sie das Ermitteln des Ursprungs von bestimmten Programmierkonstrukten in den verknüpften partiellen Klassen in der kompilierten Anwendung.  
  
 Ereignishandler in der abgeleiteten Klasse muss `internal override` (`Friend Overrides` in Microsoft Visual Basic) um die Stubs für die Handler zu überschreiben, wie in der Zwischenklasse während der Kompilierung erstellt. Andernfalls Implementierungen der abgeleiteten Klasse ausblenden (Schattenkopien) der Zwischenklasse-Implementierung und die Zwischenklasse Handler nicht aufgerufen werden.  
  
 Wenn Sie beide definieren `x:Class` und `x:Subclass`, Sie müssen keine Implementierung für die Klasse zur Verfügung gestellt, die vom verwiesen wird `x:Class`. Sie müssen nur über Benennen der `x:Class` Attribut, damit der Compiler hilfreiche Informationen für die Klasse hat, das in dem temporären Dateien erstellt wird (der Compiler ist nicht wählen Sie einen Standardnamen in diesem Fall). Sie erhalten die `x:Class` ein-klassenimplementierung; Dies ist jedoch nicht der typische Einsatzzweck für beide `x:Class` und `x:Subclass`.  
  
## <a name="see-also"></a>Siehe auch  
 [x:Class-Anweisung](../../../docs/framework/xaml-services/x-class-directive.md)  
 [XAML- und benutzerdefinierte Klassen für WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
