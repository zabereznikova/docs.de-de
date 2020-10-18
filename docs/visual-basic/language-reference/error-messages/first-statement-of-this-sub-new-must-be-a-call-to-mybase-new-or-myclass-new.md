---
title: Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: bce8ad10bc201386f34d6623741c7d41a5dec27e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163024"
---
# <a name="bc30148-first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a>BC30148: die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase. New" oder "MyClass. New" sein (kein zugreif barer Konstruktor ohne Parameter).

Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase. New" oder "MyClass. New" sein, da die Basisklasse "" \<basename> von "" keine zugreif Bare \<derivedname> "Sub New" hat, die ohne Argumente aufgerufen werden kann.

 In einer abgeleiteten Klasse muss jeder Konstruktor einen Basisklassenkonstruktor () aufzurufen `MyBase.New` . Wenn die Basisklasse über einen Konstruktor ohne Parameter verfügt, auf den abgeleitete Klassen zugegriffen `MyBase.New` werden kann, kann automatisch aufgerufen werden. Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch erfolgen. In diesem Fall muss die erste Anweisung jedes abgeleiteten Klassenkonstruktors einen parametrisierten Konstruktor für die Basisklasse oder einen anderen Konstruktor in der abgeleiteten Klasse, der einen basisklassenkonstruktoraufzurufen, aufruft.

 **Fehler-ID:** BC30148

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenden Sie entweder an `MyBase.New` , um die erforderlichen Parameter anzugeben, oder nennen Sie einen Peerkonstruktor, der einen solchen aufruft.

     Wenn die Basisklasse z. b. über einen Konstruktor verfügt, der als deklariert ist `Public Sub New(ByVal index as Integer)` , kann die erste Anweisung im Konstruktor der abgeleiteten Klasse sein `MyBase.New(100)` .

## <a name="see-also"></a>Siehe auch

- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
