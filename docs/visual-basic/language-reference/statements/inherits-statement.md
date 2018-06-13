---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 43a8aa4e9e04ee035cb52e9f829de13e5c022217
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604340"
---
# <a name="inherits-statement"></a>Inherits Statement
Bewirkt, dass die aktuelle Klasse oder Schnittstelle, um die Attribute, Variablen, Eigenschaften, Prozeduren und Ereignisse von einer anderen Klasse oder Gruppe von Schnittstellen erben.  
  
## <a name="syntax"></a>Syntax  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`basetypenames`|Erforderlich. Der Name der Klasse, von der diese Klasse abgeleitet wird.<br /><br /> - oder - <br /><br /> Die Namen der Schnittstellen, die von denen diese Schnittstelle abgeleitet wird. Verwenden Sie Kommas zum Trennen Sie mehrere Namen ein.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn verwendet, die `Inherits` -Anweisung muss die erste nicht leere, nicht kommentierten Zeile in der Definition einer Klasse oder Schnittstelle sein. Folgen sie sofort die `Class` oder `Interface` Anweisung.  
  
 Sie können `Inherits` nur in einer Klasse oder Schnittstelle. Dies bedeutet, dass der Deklarationskontext für Vererbung eine Quelldatei, Namespace, Struktur, Modul, Prozedur oder Block nicht möglich.  
  
## <a name="rules"></a>Regeln  
  
-   **Klassenvererbung.** Wenn einer Klasse verwendet die `Inherits` -Anweisung können Sie nur eine Basisklasse angeben.  
  
     Eine Klasse kann nicht von einer Klasse, die in ihr geschachtelt erben.  
  
-   **Schnittstellenvererbung.** Wenn eine Schnittstelle verwendet, die `Inherits` -Anweisung können Sie eine oder mehrere Basisschnittstellen angeben. Sie können von zwei Schnittstellen erben, auch wenn sie jeweils ein Element mit demselben Namen definieren. In diesem Fall muss der implementierende Code Namensqualifikation verwenden, um die Member anzugeben implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer stärker einschränkende Zugriffsebene erben. Z. B. eine `Public` Schnittstelle kann nicht Vererben eine `Friend` Schnittstelle.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle, die in ihr geschachtelt erben.  
  
 Ein Beispiel der klassenvererbung in .NET Framework ist die <xref:System.ArgumentException> -Klasse, die erbt die <xref:System.SystemException> Klasse. Dies ermöglicht auf <xref:System.ArgumentException> alle vordefinierten Eigenschaften und Prozeduren, die erforderlichen Systemausnahmen, z. B. die <xref:System.Exception.Message%2A> Eigenschaft und die <xref:System.Exception.ToString%2A> Methode.  
  
 Ein Beispiel für schnittstellenvererbung in .NET Framework ist die <xref:System.Collections.ICollection> -Schnittstelle, die erbt die <xref:System.Collections.IEnumerable> Schnittstelle. Dies bewirkt, dass <xref:System.Collections.ICollection> erben die Definition der Enumerator zum Durchlaufen einer Auflistung erforderlich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Inherits` Anweisung, um anzuzeigen, wie eine Klasse mit dem Namen `thisClass` können alle Member der Basisklasse erben `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Vererbung von mehreren Schnittstellen.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 Die Schnittstelle mit dem Namen `thisInterface` enthält jetzt alle Definitionen in der <xref:System.IComparable>, <xref:System.IDisposable>, und <xref:System.IFormattable> Schnittstellen, die die geerbten Member bzw. für typspezifische Vergleich von zwei Objekten bereitstellen: Freigeben von zugeordneten Ressourcen , und geben den Wert eines Objekts als ein `String`. Eine Klasse, die implementiert `thisInterface` muss jedes Mitglied jeder Basisschnittstelle implementieren.  
  
## <a name="see-also"></a>Siehe auch  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
