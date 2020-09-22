---
title: Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: e336494ad78e9835f62ad54bb4dbf91a63172a25
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874110"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a>Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase.New" oder "MyClass.New" sein (Zugriff auf Konstruktor ohne Parameter nicht möglich)

Die erste Anweisung dieses "Sub New" muss ein Aufruf an "MyBase. New" oder "MyClass. New" sein, da die Basisklasse "" \<basename> von "" keine zugreif Bare \<derivedname> "Sub New" hat, die ohne Argumente aufgerufen werden kann.  
  
 In einer abgeleiteten Klasse muss jeder Konstruktor einen Basisklassenkonstruktor () aufzurufen `MyBase.New` . Wenn die Basisklasse über einen Konstruktor ohne Parameter verfügt, auf den abgeleitete Klassen zugegriffen `MyBase.New` werden kann, kann automatisch aufgerufen werden. Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch erfolgen. In diesem Fall muss die erste Anweisung jedes abgeleiteten Klassenkonstruktors einen parametrisierten Konstruktor für die Basisklasse oder einen anderen Konstruktor in der abgeleiteten Klasse, der einen basisklassenkonstruktoraufzurufen, aufruft.  
  
 **Fehler-ID:** BC30148  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenden Sie entweder an `MyBase.New` , um die erforderlichen Parameter anzugeben, oder nennen Sie einen Peerkonstruktor, der einen solchen aufruft.  
  
     Wenn die Basisklasse z. b. über einen Konstruktor verfügt, der als deklariert ist `Public Sub New(ByVal index as Integer)` , kann die erste Anweisung im Konstruktor der abgeleiteten Klasse sein `MyBase.New(100)` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
