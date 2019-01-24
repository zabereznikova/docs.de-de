---
title: Unterschiede zwischen Shadowing und Überschreiben (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: d60d668c97019418b30b89147e86f7beea1c31f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640676"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Unterschiede zwischen Shadowing und Überschreiben (Visual Basic)
Wenn Sie eine Klasse, die von einer Basisklasse erbt definieren, möchten Sie manchmal eine oder mehrere Elemente der Basisklasse in der abgeleiteten Klasse neu zu definieren. Shadowing und überschreiben sind verfügbar für diesen Zweck.  
  
## <a name="comparison"></a>Vergleich  
 Shadowing und überschreiben werden verwendet, wenn eine abgeleitete Klasse, die von einer Basisklasse erbt, und beide einen deklariertes Element mit einem anderen neu definieren. Es gibt jedoch bedeutende Unterschiede zwischen den beiden.  
  
 Die folgende Tabelle vergleicht das shadowing und überschreiben.  
  
||||  
|---|---|---|  
|Zum Vergleich|Shadowing|Überschreiben|  
|Zweck|Schützt eine spätere Änderung Basisklasse, die einen Member einführen, die, den Sie bereits in der abgeleiteten Klasse definiert haben|Polymorphie erreicht, definieren Sie eine andere Implementierung einer Prozedur oder Eigenschaft mit dem gleichen Aufrufsequenz<sup>1</sup>|  
|Neu definierte element|Jeder deklarierte Typ des Elements|Nur eine Prozedur (`Function`, `Sub`, oder `Operator`) oder eine Eigenschaft|  
|Redefine-element|Jeder deklarierte Typ des Elements|Nur eine Prozedur oder Eigenschaft mit einer identischen Aufrufabfolge<sup>1</sup>|  
|Die Zugriffsebene des neu definierenden Elements|Zugriffsebene|Zugriffsebene außer Kraft gesetztes Element kann nicht geändert werden.|  
|LES- und schreibbarkeit des neu definierenden Elements|Eine beliebige Kombination|Lesbarkeit und schreibbarkeit der überschriebenen Eigenschaft kann nicht geändert werden.|  
|Kontrolle über die Neudefinition|Basisklasse-Element kann nicht zu erzwingen oder verbieten shadowing|Basisklassenelement festlegbaren `MustOverride`, `NotOverridable`, oder `Overridable`|  
|Verwendung von Schlüsselwörtern|`Shadows` in der abgeleiteten Klasse empfohlen; `Shadows` angenommen, wenn keines von beiden `Shadows` noch `Overrides` angegebenen<sup>2</sup>|`Overridable` oder `MustOverride` erforderlich sind, in der Basisklasse; `Overrides` in einer abgeleiteten Klasse erforderlich|  
|Die Vererbung des neu definierenden Elements von der abgeleiteten Klasse abgeleitete Klassen|Shadowing-Element von geerbt weiter abgeleiteten Klassen; schattiertes Element weiterhin ausgeblendet<sup>3</sup>|Element Überschreiben von geerbten weiter abgeleiteten Klassen; außer Kraft gesetztes Element immer noch überschreiben.|  
  
 <sup>1</sup> der *Aufrufabfolge* besteht aus den Elementtyp (`Function`, `Sub`, `Operator`, oder `Property`), name, der Parameterliste, und den Rückgabetyp. Eine Prozedur mit einer Eigenschaft oder umgekehrt kann nicht überschrieben werden. Eine Art von Prozedur kann nicht überschrieben werden (`Function`, `Sub`, oder `Operator`) mit einer anderen Art.  
  
 <sup>2</sup> , wenn Sie nicht entweder angeben `Shadows` oder `Overrides`, gibt der Compiler eine Warnmeldung an, die Ihnen bei der achten, welche Art von Neudefinition, die Sie verwenden möchten. Wenn Sie die Warnung ignorieren, wird das Shadowing verwendet.  
  
 <sup>3</sup> ist das shadowing-Element kann nicht zugegriffen werden, in einer abgeleiteten Klasse weiter, die Spiegelung wird nicht geerbt. Angenommen, Sie deklarieren, dass das shadowing-Element als `Private`, eine Klasse, die von der abgeleiteten Klasse erbt das ursprüngliche Element statt das shadowing-Element.  
  
## <a name="guidelines"></a>Richtlinien  
 Normalerweise verwenden Sie in den folgenden Fällen überschreiben:  
  
-   Definieren Sie polymorphe abgeleitete Klassen.  
  
-   Sie möchten die Sicherheit, dass des Compilers den gleichen Elementtyp und Aufrufsequenz zu erzwingen.  
  
 Normalerweise verwenden Sie shadowing in den folgenden Fällen:  
  
-   Sie erwarten, dass Ihre Basisklasse geändert werden kann, und definieren ein Element mit dem gleichen Namen wie Ihre.  
  
-   Sie möchten die Freiheit der Typ des Elements zu ändern oder das Aufrufen der Sequenz.  
  
## <a name="see-also"></a>Siehe auch
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Vorgehensweise: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
