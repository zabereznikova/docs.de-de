---
title: Erbt-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: e92e12908c89bb7a0bf385a2122b0c8f1eb8a6f7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581757"
---
# <a name="inherits-statement"></a>Inherits Statement
Bewirkt, dass die aktuelle Klasse oder Schnittstelle die Attribute, Variablen, Eigenschaften, Prozeduren und Ereignisse von einer anderen Klasse oder Gruppe von Schnittstellen erbt.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`basetypenames`|Erforderlich. Der Name der Klasse, von der diese Klasse abgeleitet wird.<br /><br /> - oder -<br /><br /> Die Namen der Schnittstellen, von denen diese Schnittstelle abgeleitet ist. Trennen Sie mehrere Namen mithilfe von Kommas.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `Inherits`-Anweisung verwendet wird, muss es sich um die erste nicht leere Zeile, die keine Kommentarzeile in einer Klassen-oder Schnittstellen Definition ist. Er sollte direkt der `Class`-oder `Interface`-Anweisung folgen.  
  
 Sie können `Inherits` nur in einer Klasse oder Schnittstelle verwenden. Dies bedeutet, dass der Deklarations Kontext für eine Vererbung keine Quelldatei, ein Namespace, eine Struktur, ein Modul, eine Prozedur oder ein Block sein kann.  
  
## <a name="rules"></a>Regeln  
  
- **Klassen Vererbung.** Wenn eine Klasse die `Inherits`-Anweisung verwendet, können Sie nur eine Basisklasse angeben.  
  
     Eine Klasse kann nicht von einer Klasse erben, die darin geschachtelt ist.  
  
- **Schnittstellen Vererbung.** Wenn eine Schnittstelle die `Inherits`-Anweisung verwendet, können Sie eine oder mehrere Basis Schnittstellen angeben. Sie können von zwei Schnittstellen erben, auch wenn Sie jeweils einen Member mit demselben Namen definieren. Wenn Sie dies tun, muss der implementierende Code die namens Qualifizierung verwenden, um anzugeben, welcher Member implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer restriktiveren Zugriffsebene erben. Beispielsweise kann eine `Public`-Schnittstelle nicht von einer `Friend`-Schnittstelle erben.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle erben, die darin geschachtelt ist.  
  
 Ein Beispiel für die Klassen Vererbung in der .NET Framework ist die <xref:System.ArgumentException> Klasse, die von der <xref:System.SystemException>-Klasse erbt. Dadurch werden alle vordefinierten Eigenschaften und Prozeduren <xref:System.ArgumentException>, die für System Ausnahmen erforderlich sind, wie z. b. die <xref:System.Exception.Message%2A>-Eigenschaft und die <xref:System.Exception.ToString%2A>-Methode.  
  
 Ein Beispiel für eine Schnittstellen Vererbung in der .NET Framework ist die <xref:System.Collections.ICollection>-Schnittstelle, die von der <xref:System.Collections.IEnumerable>-Schnittstelle erbt. Dies bewirkt, dass <xref:System.Collections.ICollection> die Definition des Enumerators erbt, der zum Durchlaufen einer Auflistung erforderlich ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Inherits`-Anweisung verwendet, um anzuzeigen, wie eine Klasse mit dem Namen `thisClass` alle Member einer Basisklasse mit dem Namen `anotherClass` erben kann.  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Vererbung mehrerer Schnittstellen.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 Die-Schnittstelle mit dem Namen "`thisInterface`" enthält jetzt alle Definitionen der Schnittstellen "<xref:System.IComparable>", "<xref:System.IDisposable>" und "<xref:System.IFormattable>", die die geerbten Member für typspezifische Vergleiche von zwei Objekten bereitstellen, zugeordnete Ressourcen freigeben und den Wert von ein-Objekt als `String`. Eine Klasse, die `thisInterface` implementiert, muss jeden Member jeder Basisschnittstelle implementieren.  
  
## <a name="see-also"></a>Siehe auch

- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
