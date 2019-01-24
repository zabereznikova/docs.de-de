---
title: Die erste Anweisung dieser &#39;Sub New&#39; muss ein Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; (Konstruktor ohne Parameter nicht möglich)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 75832ae88908094c1cb74ce04ad84c0d2ae91e68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728894"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>Die erste Anweisung dieser &#39;Sub New&#39; muss ein Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; (Konstruktor ohne Parameter nicht möglich)
Die erste Anweisung dieser "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da Basisklasse\<Basename >' von '\<Derivedname >' verfügt nicht über zugegriffen werden kann 'Sub New"hat, die ohne Argumente aufgerufen werden kann.  
  
 Jeder Konstruktor muss in einer abgeleiteten Klasse einen Basisklassenkonstruktor aufrufen (`MyBase.New`). Wenn die Basisklasse der Klasse einen Konstruktor ohne Parameter verfügt, die abgeleiteten Klassen zugänglich ist `MyBase.New` automatisch aufgerufen werden kann. Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch durchgeführt werden. In diesem Fall muss die erste Anweisung jeder abgeleiteten Klassenkonstruktor einen parametrisierten Konstruktor der Basisklasse aufrufen, oder rufen einen anderen Konstruktor in der abgeleiteten Klasse, mit der ein Konstruktor der Basisklasse aufrufen.  
  
 **Fehler-ID:** BC30148  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entweder Aufruf `MyBase.New` Angabe der erforderlichen Parameter, oder rufen Sie einen Peerkonstruktor, der solchen Aufruf ausführt.  
  
     Wenn die Basisklasse der Klasse einen Konstruktor verfügt, die als deklariert wird z. B. `Public Sub New(ByVal index as Integer)`, wird die erste Anweisung in der abgeleiteten Klassenkonstruktor möglicherweise `MyBase.New(100)`.  
  
## <a name="see-also"></a>Siehe auch
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
