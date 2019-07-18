---
title: Systeminterner x:Code-XAML-Typ
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: f6898008fa3e3e7e385a2bc77c5b2eac7eeda2ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617159"
---
# <a name="xcode-intrinsic-xaml-type"></a>Systeminterner x:Code-XAML-Typ
Ermöglicht die Platzierung von Code innerhalb einer XAML-Produktion. Dieser Code kann entweder von einer Implementierung der XAML-Prozessor kompiliert werden, die XAML, oder von links in der XAML-Produktion zur späteren Verwendung für z.B. Interpretation von einer Runtime kompiliert wird.  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Code innerhalb der `x:Code` XAML-Anweisungselement ist immer noch innerhalb der allgemeinen XML-Namespace interpretiert und die XAML-Namespaces zur Verfügung gestellt. Daher ist es normalerweise notwendig, schließen Sie den Code zum `x:Code` innerhalb einer `CDATA` Segment.  
  
 `x:Code` ist für alle möglichen Bereitstellungsmechanismen einer XAML-Produktion nicht zulässig. In bestimmten Frameworks (z. B. WPF) muss der Code kompiliert werden. In anderen Frameworks `x:Code` Nutzung kann im Allgemeinen als unzulässig erklärt werden.  
  
 Für Frameworks, mit denen verwaltete `x:Code` Inhalt, für die Verwendung der richtigen Sprachcompiler `x:Code` Inhalt richtet sich nach den Einstellungen und Ziele des enthaltenden Projekts, das verwendet wird, um die Anwendung zu kompilieren.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Code deklariert in `x:Code` für WPF mehrere wichtige Einschränkungen aufweist:  
  
- Die `x:Code` -Anweisungselement muss ein unmittelbar untergeordnetes Element des Stammelements der XAML-Produktion sein.  
  
- [X: Class-Anweisung](x-class-directive.md) muss für das Stammelement der übergeordneten bereitgestellt werden.  
  
- Der Code eingefügt, in `x:Code` behandelt werden, von der Kompilierung innerhalb des Bereichs der partiellen Klasse sein, die bereits für diese XAML-Seite erstellt wird. Aus diesem Grund muss alle Code, den Sie definieren, Member oder Variablen der partiellen Klasse sein.  
  
- Sie können keine zusätzliche Klassen definieren, als durch das Schachteln einer Klasse in der partiellen Klasse (Schachtelung ist zulässig, aber es ist nicht typisch, da geschachtelte Klassen in XAML verwiesen werden können). CLR-Namespaces als dem, der für die vorhandene partielle Klasse verwendet wird, kann nicht definiert oder hinzugefügt werden.  
  
- Verweise auf Entitäten außerhalb der partiellen Klasse CLR-Namespace müssen alle vollqualifiziert sein. Wenn Mitglieder, die deklariert wird, überschreibungen, um die partielle Klasse überschreibbare Member sind, muss dies mit dem sprachspezifischen Override-Schlüsselwort angegeben werden. Wenn Sie im Member deklariert `x:Code` Bereich in Konflikt mit Membern der partiellen Klasse aus dem XAML erstellt, so, dass der Compiler den Konflikt, meldet die XAML-Datei kann nicht kompiliert oder geladen.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Übersicht über XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
