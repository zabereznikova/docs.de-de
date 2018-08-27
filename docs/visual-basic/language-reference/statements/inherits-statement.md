---
title: Inherits-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 4a98ada39a04730b46f40fe139e72d1855d9b067
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931234"
---
# <a name="inherits-statement"></a>Inherits Statement
Bewirkt, dass die aktuelle Klasse bzw. Schnittstelle der Attribute, Variablen, Eigenschaften, Prozeduren und Ereignisse von einer anderen Klasse oder Gruppe von Schnittstellen erbt.  
  
## <a name="syntax"></a>Syntax  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`basetypenames`|Erforderlich. Der Name der Klasse, aus der dieser Klasse abgeleitet wird.<br /><br /> - oder - <br /><br /> Die Namen der Schnittstellen, die von denen diese Schnittstelle abgeleitet wird. Verwenden Sie Kommas zum Trennen mehrere Namen ein.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn verwendet, die `Inherits` -Anweisung muss die erste nicht leere, nicht kommentierten Zeile in der Definition einer Klasse oder Schnittstelle sein. Es sollte unmittelbar folgen der `Class` oder `Interface` Anweisung.  
  
 Sie können `Inherits` nur in einer Klasse oder Schnittstelle. Dies bedeutet, dass der Deklarationskontext für Vererbung eine Quelldatei, Namespace, Struktur, Modul, Prozedur oder Block kann nicht.  
  
## <a name="rules"></a>Regeln  
  
-   **Klassenvererbung.** Wenn eine Klasse verwendet die `Inherits` -Anweisung können Sie nur eine Basisklasse angeben.  
  
     Eine Klasse kann nicht von einer Klasse, die in ihr geschachtelt ist, erben.  
  
-   **Schnittstellenvererbung.** Wenn eine Schnittstelle verwendet die `Inherits` -Anweisung können Sie einem oder mehreren Basisschnittstellen angeben. Sie können über zwei Schnittstellen erben, auch wenn sie jeweils einen Member mit demselben Namen definieren. Wenn Sie dies tun, muss der implementierende Code Namensqualifikation verwenden Sie zum Angeben von der Members implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer stärker einschränkende Zugriffsebene erben. Z. B. eine `Public` Schnittstelle kann nicht erben von einem `Friend` Schnittstelle.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle, die in ihr geschachtelt ist, erben.  
  
 Ein Beispiel für klassenvererbung in .NET Framework ist die <xref:System.ArgumentException> -Klasse, die erbt die <xref:System.SystemException> Klasse. Dies bietet auf <xref:System.ArgumentException> alle vordefinierte Eigenschaften und Prozeduren, die Systemausnahmen, erforderlich sind, z. B. die <xref:System.Exception.Message%2A> Eigenschaft und die <xref:System.Exception.ToString%2A> Methode.  
  
 Ein Beispiel für schnittstellenvererbung in .NET Framework ist die <xref:System.Collections.ICollection> -Schnittstelle, die erbt die <xref:System.Collections.IEnumerable> Schnittstelle. Dies bewirkt, dass <xref:System.Collections.ICollection> erben von der Definition der Enumerator zum Durchlaufen einer Auflistung erforderlich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Inherits` Anweisung, um zu zeigen, wie eine Klasse namens `thisClass` können alle Member der Basisklasse erben `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Vererbung von mehreren Schnittstellen.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 Die Schnittstelle, die mit dem Namen `thisInterface` enthält jetzt alle Definitionen in der <xref:System.IComparable>, <xref:System.IDisposable>, und <xref:System.IFormattable> Schnittstellen die geerbten Member bzw. ein typenspezifisches Vergleich von zwei Objekten Freigeben von zugeordneten Ressourcen , und deren Ausdruck des Werts eines Objekts als ein `String`. Eine Klasse, die implementiert `thisInterface` müssen alle Member jeder Basisschnittstelle implementieren.  
  
## <a name="see-also"></a>Siehe auch  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
