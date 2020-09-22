---
title: <membername> kann den <typename>-Typ nicht außerhalb des Projekts über <containertype> "<containertypename>" verfügbar machen.
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 31d44c93d62163df4d81cb8503b633f0eb317372
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873806"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>\<membername> kann den \<typename>-Typ nicht außerhalb des Projekts über \<containertype> "\<containertypename>" verfügbar machen.

Eine Variable, ein Prozedur Parameter oder eine Funktions Rückgabe wird außerhalb ihres Containers verfügbar gemacht, Sie wird jedoch als Typ deklariert, der nicht außerhalb des Containers verfügbar gemacht werden darf.  
  
 Der folgende Skelett Code zeigt eine Situation, die diesen Fehler generiert.  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Ein Typ, der als `Protected` ,, oder deklariert ist, soll `Friend` `Protected Friend` `Private` eingeschränkten Zugriff außerhalb des Deklarations Kontexts haben. Die Verwendung als Datentyp einer Variablen mit weniger eingeschränktem Zugriff würde diesen Zweck zunichte machen. Im obigen Skelett Code ist, `exposedVar` `Public` und würde für Code verfügbar machen, `privateClass` der keinen Zugriff darauf haben sollte.  
  
 **Fehler-ID:** BC30909  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Ändern Sie die Zugriffsebene der Variablen, des Prozedur Parameters oder der Funktions Rückgabe so, dass Sie mindestens so restriktiv ist wie die Zugriffsebene des Datentyps.  
  
## <a name="see-also"></a>Weitere Informationen

- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
