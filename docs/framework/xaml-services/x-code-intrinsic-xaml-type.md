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
ms.openlocfilehash: 2b7713548b6269f079ef32b5bf1fe4fa630edcc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053796"
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
 Der Code im `x:Code` XAML-Direktivenelement wird immer noch innerhalb des allgemeinen XML-Namespace und der bereitgestellten XAML-Namespaces interpretiert. Daher ist es normalerweise erforderlich, den Code, der für `x:Code` innerhalb eines `CDATA` Segments verwendet wird, einzuschließen.  
  
 `x:Code`ist nicht für alle möglichen Bereitstellungs Mechanismen einer XAML-Produktion zulässig. In bestimmten Frameworks (z. b. WPF) muss der Code kompiliert werden. In anderen Frameworks `x:Code` ist die Verwendung möglicherweise in der Regel nicht zulässig.  
  
 Für Frameworks, die `x:Code` verwalteten Inhalt zulassen, wird der korrekte sprach Compiler `x:Code` , der für-Inhalte verwendet wird, durch Einstellungen und Ziele des enthaltenden Projekts bestimmt, das zum Kompilieren der Anwendung verwendet wird.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 Der in `x:Code` für WPF deklarierte Code hat mehrere wichtige Einschränkungen:  
  
- Das `x:Code` Direktivenelement muss ein unmittelbares untergeordnetes Element des Stamm Elements der XAML-Produktion sein.  
  
- die [x:Class-Direktive](x-class-directive.md) muss für das übergeordnete root-Element bereitgestellt werden.  
  
- Der in `x:Code` platzierte Code wird von der Kompilierung behandelt, um innerhalb des Bereichs der partiellen Klasse zu sein, die bereits für diese XAML-Seite erstellt wurde. Daher müssen alle von Ihnen definierten Codes Member oder Variablen dieser partiellen Klasse sein.  
  
- Sie können keine zusätzlichen Klassen definieren, außer indem Sie eine Klasse in der partiellen Klasse Schachteln (die Schachtelung ist zulässig, aber nicht typisch, weil auf geschachtelte Klassen in XAML nicht verwiesen werden kann). Andere CLR-Namespaces als der Namespace, der für die vorhandene partielle Klasse verwendet wird, können nicht definiert oder zu hinzugefügt werden.  
  
- Verweise auf Code Entitäten außerhalb des CLR-Namespace der partiellen Klasse müssen alle voll qualifiziert sein. Wenn Member, die deklariert werden, über Schreibungen für die partiell baren Member der partiellen Klasse sind, muss dies mit dem sprachspezifischen Überschreibungs Schlüsselwort angegeben werden. Wenn im `x:Code` Bereich deklarierte Member mit Membern der partiellen Klasse, die aus dem XAML erstellt wurden, so in Konflikt stehen, dass der Compiler den Konflikt meldet, kann die XAML-Datei nicht kompiliert oder geladen werden.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Übersicht über XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
