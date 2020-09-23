---
title: Unterschiede zwischen Shadowing und Überschreiben
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 98c073f8fa403416b2425431ff4334b990726f44
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095446"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Unterschiede zwischen Shadowing und Überschreiben (Visual Basic)

Wenn Sie eine Klasse definieren, die von einer Basisklasse erbt, empfiehlt es sich, ein oder mehrere der Basisklassen Elemente in der abgeleiteten Klasse neu zu definieren. Zu diesem Zweck sind auch shadodown und überschreiben verfügbar.  
  
## <a name="comparison"></a>Vergleich  

 Shadodown und überschreiben werden sowohl verwendet, wenn eine abgeleitete Klasse von einer Basisklasse erbt, als auch ein deklariertes Element mit einem anderen neu definieren. Es gibt jedoch bedeutende Unterschiede zwischen den beiden.  
  
 In der folgenden Tabelle wird shadodown mit überschreiben verglichen.  
  
||||  
|---|---|---|  
|Vergleichspunkt|Shadowing|Überschreiben|  
|Zweck|Schützt gegen eine nachfolgende Änderung der Basisklasse, die einen Member einführt, den Sie bereits in der abgeleiteten Klasse definiert haben.|Erreicht Polymorphie durch Definieren einer anderen Implementierung einer Prozedur oder Eigenschaft mit derselben Aufruf Sequenz<sup>1</sup>|  
|Neu definiertes Element|Beliebiger deklarierter Elementtyp|Nur eine Prozedur ( `Function` , `Sub` oder `Operator` ) oder eine Eigenschaft|  
|Neu definierendes Element|Beliebiger deklarierter Elementtyp|Nur eine Prozedur oder Eigenschaft mit der identischen Aufruf Sequenz<sup>1</sup>|  
|Zugriffsebene des neu definierenden Elements|Beliebige Zugriffsebene|Zugriffsebene des überschriebenen Elements kann nicht geändert werden.|  
|Lesbarkeit und Schreib barkeit des neu definierenden Elements|Beliebige Kombination|Die Lesbarkeit oder Schreib barkeit der überschriebenen Eigenschaft kann nicht geändert werden.|  
|Steuern der Neudefinition|Das Basisklassen Element kann Shadowing nicht erzwingen oder verbieten.|Das Basisklassen Element kann `MustOverride` , `NotOverridable` oder angeben. `Overridable`|  
|Schlüsselwort Verwendung|`Shadows` empfohlen in abgeleiteter Klasse; `Shadows` wird angenommen, wenn weder `Shadows` noch `Overrides` angegeben<sup>2</sup>|`Overridable` oder `MustOverride` in Basisklasse erforderlich; `Overrides` in abgeleiteter Klasse erforderlich|  
|Vererbung des neu definierenden Elements durch Klassen, die von der abgeleiteten Klasse abgeleitet werden|Shadowingelement, das von weiteren abgeleiteten Klassen geerbt wird. Shadowing Element immer noch ausgeblendet<sup>3</sup>|Überschreiben von weitergeleiteten Klassen geerbten Elementen; überschriebener Element wird immer noch überschrieben|  
  
 <sup>1</sup> die *Aufruf Sequenz* besteht aus dem Elementtyp ( `Function` , `Sub` , `Operator` , oder `Property` ), dem Namen, der Parameterliste und dem Rückgabetyp. Es ist nicht möglich, eine Prozedur mit einer-Eigenschaft oder umgekehrt zu überschreiben. Es ist nicht möglich, eine Art von Prozedur ( `Function` , `Sub` oder `Operator` ) mit einer anderen Art zu überschreiben.  
  
 <sup>2</sup> Wenn Sie weder `Shadows` noch angeben `Overrides` , gibt der Compiler eine Warnmeldung aus, um sicherzustellen, welche Art von Neudefinition Sie verwenden möchten. Wenn Sie die Warnung ignorieren, wird der shadodown-Mechanismus verwendet.  
  
 <sup>3</sup> wenn in einer weiteren abgeleiteten Klasse nicht auf das Shadowingelement zugegriffen werden kann, wird shadowingnicht geerbt. Wenn Sie z. b. das Shadowingelement als deklarieren `Private` , erbt eine Klasse, die von der abgeleiteten Klasse abgeleitet wird, das ursprüngliche-Element anstelle des Shadowing-Elements.  
  
## <a name="guidelines"></a>Richtlinien  

 In den folgenden Fällen verwenden Sie in der Regel das Überschreiben:  
  
- Sie definieren polymorphe abgeleitete Klassen.  
  
- Sie möchten, dass der Compiler den identischen Elementtyp und die gleiche Aufruf Sequenz erzwingt.  
  
 Normalerweise verwenden Sie shadowingin den folgenden Fällen:  
  
- Sie erwarten, dass die Basisklasse geändert wird, und definieren ein Element mit dem gleichen Namen wie Ihr.  
  
- Sie möchten die Freiheit ändern, den Elementtyp oder die Aufruf Sequenz zu ändern.  
  
## <a name="see-also"></a>Siehe auch

- [References to Declared Elements](references-to-declared-elements.md)
- [Shadowing in Visual Basic](shadowing.md)
- [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Vorgehensweise: Ausblenden einer geerbten Variablen](how-to-hide-an-inherited-variable.md)
- [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [Überschreibt](../../../language-reference/modifiers/overrides.md)
