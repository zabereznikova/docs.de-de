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
ms.openlocfilehash: 7312c59cdcddfdbda39a4a9f05788b6a021f9b75
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459584"
---
# <a name="xcode-intrinsic-xaml-type"></a>Systeminterner x:Code-XAML-Typ
Ermöglicht die Platzierung von Code in einer XAML-Produktion. Dieser Code kann entweder von jeder XAML-Prozessor Implementierung kompiliert werden, die XAML kompiliert, oder in der XAML-Produktion verbleiben, um später verwendet zu werden, z. b. die Interpretation durch eine Laufzeit.  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Code im `x:Code` XAML-Direktivenelement wird immer noch innerhalb des allgemeinen XML-Namespace und der bereitgestellten XAML-Namespaces interpretiert. Daher ist es in der Regel notwendig, den Code, der für die `x:Code` in einem `CDATA` Segment verwendet wird, einzuschließen.  
  
 `x:Code` ist nicht für alle möglichen Bereitstellungs Mechanismen einer XAML-Produktion zulässig. In bestimmten Frameworks (z. b. WPF) muss der Code kompiliert werden. In anderen Frameworks kann die Verwendung von `x:Code` in der Regel nicht zulässig sein.  
  
 Für Frameworks, die verwalteten `x:Code` Inhalt zulassen, wird der korrekte sprach Compiler, der für `x:Code` Inhalt verwendet wird, durch die Einstellungen und Ziele des enthaltenden Projekts bestimmt, das zum Kompilieren der Anwendung verwendet wird.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Der in `x:Code` für WPF deklarierte Code hat mehrere wichtige Einschränkungen:  
  
- Das `x:Code` Directive-Element muss ein unmittelbares untergeordnetes Element des Stamm Elements der XAML-Produktion sein.  
  
- die [x:Class-Direktive](x-class-directive.md) muss für das übergeordnete root-Element bereitgestellt werden.  
  
- Der in `x:Code` platzierte Code wird von der Kompilierung behandelt, um innerhalb des Bereichs der partiellen Klasse zu sein, die bereits für diese XAML-Seite erstellt wurde. Daher müssen alle von Ihnen definierten Codes Member oder Variablen dieser partiellen Klasse sein.  
  
- Sie können keine zusätzlichen Klassen definieren, außer indem Sie eine Klasse in der partiellen Klasse Schachteln (die Schachtelung ist zulässig, aber nicht typisch, weil auf geschachtelte Klassen in XAML nicht verwiesen werden kann). Andere CLR-Namespaces als der Namespace, der für die vorhandene partielle Klasse verwendet wird, können nicht definiert oder zu hinzugefügt werden.  
  
- Verweise auf Code Entitäten außerhalb des CLR-Namespace der partiellen Klasse müssen alle voll qualifiziert sein. Wenn Member, die deklariert werden, über Schreibungen für die partiell baren Member der partiellen Klasse sind, muss dies mit dem sprachspezifischen Überschreibungs Schlüsselwort angegeben werden. Wenn im `x:Code` Bereich deklarierte Member in Konflikt mit Membern der partiellen Klasse stehen, die aus dem XAML-Code erstellt wurden, sodass der Compiler den Konflikt meldet, kann die XAML-Datei nicht kompiliert oder geladen werden.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Übersicht über XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
