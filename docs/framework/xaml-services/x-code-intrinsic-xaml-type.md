---
title: "x:Code Intrinsic XAML Type | Microsoft Docs"
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
  - "Code"
  - "x:Code"
  - "xCode"
helpviewer_keywords: 
  - "Code directive in XAML [XAML Services]"
  - "x:Code XAML directive element [XAML Services]"
  - "XAML [XAML Services], x:Code directive element"
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: 19
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 19
---
# x:Code Intrinsic XAML Type
Ermöglicht die Platzierung des Codes innerhalb einer XAML\-Produktion.  Solcher Code kann entweder von jeder XAML\-Prozessorimplementierung kompiliert werden, die XAML kompiliert, oder zur späteren Verwendung wie z. B. Interpretation durch eine Laufzeit, in der XAML\-Produktion belassen werden.  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## Hinweise  
 Der Code im `x:Code`\-XAML\-Direktivenelement wird trotzdem in den angegebenen XML\-Namespaces innerhalb des allgemeinen XML\-Namespace interpretiert.  Deshalb ist es normalerweise notwendig, den für `x:Code` verwendeten Code in einem `CDATA`\-Segment einzuschließen.  
  
 `x:Code` ist nicht für alle möglichen Bereitstellungsmechanismen einer XAML\-Generierung zulässig.   In bestimmten Frameworks \(z. B. WPF\) muss der Code kompiliert werden.  In anderen Frameworks könnte `x:Code`\-Verwendung im Allgemeinen nicht zugelassen sein.  
  
 Für Frameworks, die verwalteten `x:Code`\-Inhalt zulassen, wird der richtige Sprachencompiler für `x:Code`\-Inhalt von den Einstellungen und Zielen des enthaltenden Projekts bestimmt, das zum Kompilieren der Anwendung verwendet wird.  
  
## Hinweise zur WPF\-Verwendung  
 Code, der innerhalb von `x:Code` für WPF deklariert wird, verfügt über verschiedene zu beachtende Einschränkungen:  
  
-   Beim `x:Code`\-Direktivenelement muss es sich um ein unmittelbar untergeordnetes Element des XAML\-Stammelements handeln.  
  
-   [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) muss im übergeordneten Stammelement vorhanden sein.  
  
-   Der Code, der in `x:Code` gesetzt wird, wird bei der Kompilierung so behandelt, als ob er sich innerhalb des Umfangs der partiellen Klasse befindet, die für die jeweilige XAML\-Seite bereits erstellt wurde.  Deshalb muss es sich beim gesamten von Ihnen definierten Code um Member oder Variablen dieser partiellen Klasse handeln.  
  
-   Sie können zusätzliche Klassen nur durch Schachtelung einer Klasse in der partiellen Klasse festlegen \(Schachtelung ist zulässig, jedoch unüblich, da auf geschachtelte Klassen nicht in XAML verwiesen werden kann\).  Andere CLR\-Namespaces als der für die vorhandene partielle Klasse verwendete Namespace können nicht definiert oder hinzugefügt werden.  
  
-   Verweise auf Codeentitäten außerhalb des partiellen CLR\-Klassennamespace müssen jeweils vollqualifiziert sein.  Wenn es sich bei deklarierten Membern um Überschreibungen der partiellen Klasse handelt, muss dies mithilfe des sprachspezifischen Überschreibungsschlüsselworts angegeben werden.  Wenn für im `x:Code`\-Bereich deklarierte Member Konflikte mit den Membern der partiellen Klasse auftreten, die aus der XAML erstellt wurde, und der Compiler den Konflikt meldet, schlägt das Laden bzw. Kompilieren der XAML\-Datei fehl.  
  
## Siehe auch  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Code\-Behind und XAML in WPF](../../../ocs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [Übersicht über XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)