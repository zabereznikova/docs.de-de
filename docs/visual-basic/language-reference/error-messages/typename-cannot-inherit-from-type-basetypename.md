---
title: <typename> erweitert den Zugriff der Basis-<type> außerhalb der Assembly und kann daher nicht von <basetypename> "<type>" erben.
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: aa04c558abbcc4259c2821cdcbdc1669b91ffee0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402771"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>\<typename> erweitert den Zugriff der Basis-\<type> außerhalb der Assembly und kann daher nicht von \<basetypename> "\<type>" erben.
Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle, verfügt aber über eine weniger restriktive Zugriffsebene.  
  
 Eine- `Public` Schnittstelle erbt z. b. von einer- `Friend` Schnittstelle, oder eine `Protected` Klasse erbt von einer- `Private` Klasse. Dadurch wird die Basisklasse oder Schnittstelle für den Zugriff über die beabsichtigte Ebene verfügbar gemacht.  
  
 **Fehler-ID:** BC30910  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle so, dass Sie mindestens so restriktiv ist wie die der Basisklasse oder Schnittstelle.  
  
     Oder  
  
- Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die- `Inherits` Anweisung. Es ist nicht möglich, von einer eingeschränkteren Basisklasse oder Schnittstelle zu erben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Class-Anweisung](../statements/class-statement.md)
- [Interface-Anweisung](../statements/interface-statement.md)
- [Inherits Statement](../statements/inherits-statement.md)
- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
