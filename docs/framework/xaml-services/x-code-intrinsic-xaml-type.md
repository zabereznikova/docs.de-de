---
title: Systeminterner x:Code-XAML-Typ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d39249a5d1c0e230d21e6d889b92d0b57c98e2ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xcode-intrinsic-xaml-type"></a>Systeminterner x:Code-XAML-Typ
Ermöglicht die Platzierung von Code in einer XAML-Produktion. Solcher Code kann entweder durch die Implementierung einer XAML-Prozessor kompiliert werden, die XAML oder links in der die Verwendung von XAML-Produktion höher verwendet, z. B. Interpretation von einer Laufzeit kompiliert wird.  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Code innerhalb der `x:Code` -XAML-Direktivenelement ist immer noch innerhalb der allgemeinen XML-Namespace interpretiert und die Verwendung von XAML-Namespaces bereitgestellt. Daher ist es normalerweise erforderlich, schließen Sie den Code zum `x:Code` innerhalb einer `CDATA` Segment.  
  
 `x:Code`ist für alle möglichen Bereitstellungsmechanismen einer XAML-Produktion nicht zulässig. In bestimmten Frameworks (z. B. WPF) muss der Code kompiliert werden. In anderen Frameworks `x:Code` Nutzung kann im Allgemeinen nicht zulässig.  
  
 Für Frameworks, die verwaltete zulassen `x:Code` Inhalte, die richtige Sprachcompiler mit `x:Code` Inhalt richtet sich nach den Einstellungen und Ziele des enthaltenden Projekts, das verwendet wird, um die Anwendung zu kompilieren.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 In Code deklariert `x:Code` für WPF mehrere wichtige Einschränkungen hat:  
  
-   Die `x:Code` Anweisungselement muss ein unmittelbar untergeordnetes Element des Stammelements der Verwendung von XAML-Produktion.  
  
-   [X: Class-Direktive](../../../docs/framework/xaml-services/x-class-directive.md) muss auf dem übergeordneten Root-Element angegeben werden.  
  
-   Der Code Hauptvideos `x:Code` behandelt werden, von der Kompilierung innerhalb des Bereichs der partiellen Klasse sein, der bereits für die Verwendung von XAML-Seite erstellt wird. Daher muss alle Code den von Ihnen definierten Member oder Variablen der partiellen Klasse sein.  
  
-   Sie können keine zusätzliche Klassen definieren, als durch das Schachteln einer Klasse in der partiellen Klasse (Schachtelung ist zulässig, aber es ist nicht typisch, da geschachtelte Klassen in XAML verwiesen werden kann). CLR-Namespaces als dem, der für die vorhandene partielle Klasse verwendet wird, kann nicht definiert oder hinzugefügt werden.  
  
-   Verweise auf Entitäten außerhalb der partiellen Klasse CLR-Namespaces müssen alle vollqualifiziert sein. Wenn Mitglieder, die deklariert wird, überschreibungen, um die partielle Klasse überschreibbaren Membern sind, muss dies mit den sprachspezifischen Override-Schlüsselwort angegeben werden. Wenn Elemente in deklariert `x:Code` Bereich in Konflikt mit Mitgliedern der partiellen Klasse, die aus der XAML-Code erstellt, so, dass der Compiler den Konflikt, meldet die XAML-Datei kann nicht kompilieren oder geladen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [x:Class-Anweisung](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Code-Behind und XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
