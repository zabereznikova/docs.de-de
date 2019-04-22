---
title: Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: debab4e495d05a05801dd11850d0665c8bd6b299
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834321"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a>Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)
Die erste Anweisung dieser "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da Basisklasse\<Basename >' von '\<Derivedname >' verfügt nicht über zugegriffen werden kann 'Sub New"hat, die ohne Argumente aufgerufen werden kann.  
  
 Jeder Konstruktor muss in einer abgeleiteten Klasse einen Basisklassenkonstruktor aufrufen (`MyBase.New`). Wenn die Basisklasse der Klasse einen Konstruktor ohne Parameter verfügt, die abgeleiteten Klassen zugänglich ist `MyBase.New` automatisch aufgerufen werden kann. Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch durchgeführt werden. In diesem Fall muss die erste Anweisung jeder abgeleiteten Klassenkonstruktor einen parametrisierten Konstruktor der Basisklasse aufrufen, oder rufen einen anderen Konstruktor in der abgeleiteten Klasse, mit der ein Konstruktor der Basisklasse aufrufen.  
  
 **Fehler-ID:** BC30148  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entweder Aufruf `MyBase.New` Angabe der erforderlichen Parameter, oder rufen Sie einen Peerkonstruktor, der solchen Aufruf ausführt.  
  
     Wenn die Basisklasse der Klasse einen Konstruktor verfügt, die als deklariert wird z. B. `Public Sub New(ByVal index as Integer)`, wird die erste Anweisung in der abgeleiteten Klassenkonstruktor möglicherweise `MyBase.New(100)`.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
