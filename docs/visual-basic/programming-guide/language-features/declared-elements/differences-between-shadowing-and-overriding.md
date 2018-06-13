---
title: Unterschiede zwischen Shadowing und Überschreiben (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 94ce3e7fe25b7942730e6e89a53654b03d91c42b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649632"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Unterschiede zwischen Shadowing und Überschreiben (Visual Basic)
Wenn Sie eine Klasse, die von einer Basisklasse erbt definieren, möchten manchmal eine oder mehrere der in der abgeleiteten Klasse die Basisklasse-Elemente neu definieren. Shadowing und überschreiben sind verfügbar für diesen Zweck.  
  
## <a name="comparison"></a>Vergleich  
 Shadowing und überschreiben werden verwendet, wenn eine abgeleitete Klasse, die von einer Basisklasse erbt, und beide ein deklariertes Element mit einem anderen neu definieren. Es gibt jedoch bedeutende Unterschiede zwischen den beiden.  
  
 Die folgende Tabelle vergleicht shadowing und überschreiben.  
  
||||  
|---|---|---|  
|Vergleichspunkt|Shadowing|Überschreiben|  
|Zweck|Schutz gegen eine spätere Änderung Basisklasse, die ein Element eingeführt werden, die Sie in der abgeleiteten Klasse bereits definiert haben|Polymorphie erreicht, durch die Definition einer anderen Implementierung einer Prozedur oder Eigenschaft mit dem gleichen Aufrufsequenz<sup>1</sup>|  
|Neu definierten element|Jeder deklarierte Elementtyp.|Nur eine Prozedur (`Function`, `Sub`, oder `Operator`) oder eine Eigenschaft|  
|Redefine-element|Jeder deklarierte Elementtyp.|Nur eine Prozedur oder Eigenschaft mit einer identischen Aufrufabfolge<sup>1</sup>|  
|Zugriffsebene des neu definierenden Elements|Eine andere Zugriffsebene|Zugriffsebene außer Kraft gesetztes Element kann nicht geändert werden.|  
|Lese- und Schreibberechtigung für Neudefinieren-element|Eine beliebige Kombination|Lesbarkeit oder Schreibberechtigung für die überschriebenen Eigenschaft kann nicht geändert werden.|  
|Kontrolle über die Neudefinition|Basisklasse-Element kann nicht zu erzwingen und verbieten shadowing|Basisklassenelement festlegbaren `MustOverride`, `NotOverridable`, oder `Overridable`|  
|Verwendung von Schlüsselwörtern|`Shadows` in der abgeleiteten Klasse empfohlen; `Shadows` davon ausgegangen, dass weder `Shadows` noch `Overrides` angegebenen<sup>2</sup>|`Overridable` oder `MustOverride` erforderlich, in der Basisklasse; `Overrides` in einer abgeleiteten Klasse erforderlich|  
|Vererbung des neu definierenden Elements von von der abgeleiteten Klasse abgeleitete Klassen|Shadowing-Element von geerbt weiter abgeleiteten Klassen; schattiertes Element weiterhin ausgeblendet<sup>3</sup>|Element Überschreiben von geerbten weiter abgeleiteten Klassen; außer Kraft gesetztes Element noch überschreiben.|  
  
 <sup>1</sup> der *Aufrufsequenz* besteht aus den Elementtyp (`Function`, `Sub`, `Operator`, oder `Property`), benennen Sie die Parameterliste, und dem Rückgabetyp. Sie können eine Prozedur mit einer Eigenschaft oder den umgekehrten nicht überschreiben. Eine Art von Prozedur kann nicht überschrieben werden (`Function`, `Sub`, oder `Operator`) mit einer anderen Art.  
  
 <sup>2</sup> , wenn Sie nicht entweder angeben `Shadows` oder `Overrides`, der Compiler gibt eine Warnmeldung können Sie sicher sein, welche Art von Neudefinition, die Sie verwenden möchten. Wenn Sie die Warnung ignorieren, wird das Shadowing verwendet.  
  
 <sup>3</sup> ist das shadowing-Element kann nicht zugegriffen werden, in einer weiteren abgeleiteten Klasse shadowing nicht geerbt. Wenn Sie das shadowing-Element als deklarieren z. B. `Private`, eine von der abgeleiteten Klasse abgeleitete Klasse erbt das ursprüngliche Element, anstatt das shadowing-Element.  
  
## <a name="guidelines"></a>Richtlinien  
 Normalerweise verwenden Sie in den folgenden Fällen überschreiben:  
  
-   Sie definieren polymorphe abgeleitete Klassen.  
  
-   Die Sicherheit der, dass der Compiler den gleichen Elementtyp und Aufrufsequenz erzwungen werden sollen.  
  
 Normalerweise verwenden Sie shadowing in den folgenden Fällen:  
  
-   Sie erwarten, dass Ihre Basisklasse möglicherweise geändert werden, und definieren ein Element mit dem gleichen Namen wie der Ihres.  
  
-   Die Freiheit gibt den Elementtyp ändern oder die Aufrufsequenz angezeigt werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Gewusst wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
