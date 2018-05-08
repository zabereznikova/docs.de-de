---
title: Die erste Anweisung &#39;Sub New&#39; muss ein Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; (No aufrufbare Konstruktoren ohne Parameter)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 3b24385932700a4843ae295bc82ef9529cc86b9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>Die erste Anweisung &#39;Sub New&#39; muss ein Aufruf von &#39;MyBase.New&#39; oder &#39;MyClass.New&#39; (No aufrufbare Konstruktoren ohne Parameter)
Die erste Anweisung dieser "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da Basisklasse\<Basename >' von '\<Derivedname >' besitzt keine zugegriffen werden kann "Sub New" hat, die ohne Argumente aufgerufen werden kann.  
  
 Jeder Konstruktor muss in einer abgeleiteten Klasse einen Basisklassenkonstruktor aufrufen (`MyBase.New`). Wenn die Basisklasse der Klasse einen Konstruktor ohne Parameter verfügt, die für den abgeleiteten Klassen zugänglich ist `MyBase.New` automatisch aufgerufen werden kann. Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch durchgeführt werden. In diesem Fall muss die erste Anweisung jeder abgeleiteten Klassenkonstruktor einen parametrisierten Konstruktor der Basisklasse aufrufen, oder rufen Sie einen anderen Konstruktor in der abgeleiteten Klasse, mit der ein Konstruktor der Basisklasse aufrufen.  
  
 **Fehler-ID:** BC30148  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entweder Aufruf `MyBase.New` Geben Sie die erforderlichen Parameter, oder rufen Sie einen Peerkonstruktor, der solch einen Aufruf macht.  
  
     Angenommen, wenn die Basisklasse der Klasse einen Konstruktor verfügt, die als deklariert ist `Public Sub New(ByVal index as Integer)`, die erste Anweisung in der abgeleiteten Klassenkonstruktor möglicherweise `MyBase.New(100)`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
