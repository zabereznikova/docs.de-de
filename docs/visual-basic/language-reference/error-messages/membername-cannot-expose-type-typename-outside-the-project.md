---
title: <membername> kann den <typename>-Typ nicht außerhalb des Projekts über <containertype> '<containertypename>' verfügbar machen.
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: ca67e74d7790352bd1842cb8a59fe1525af6e18c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700900"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>'\<Membername >' kann nicht verfügbar machen '\<Typname >' außerhalb des Projekts durch \<Hiermit > '\<Containertypename >'
Eine Variable, ein Prozedur Parameter oder eine Funktions Rückgabe wird außerhalb ihres Containers verfügbar gemacht, Sie wird jedoch als Typ deklariert, der nicht außerhalb des Containers verfügbar gemacht werden darf.  
  
 Der folgende Skelett Code zeigt eine Situation, die diesen Fehler generiert.  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Ein Typ, der `Protected`, `Friend`, `Protected Friend` oder `Private` deklariert ist, soll nur begrenzten Zugriff außerhalb des Deklarations Kontexts haben. Die Verwendung als Datentyp einer Variablen mit weniger eingeschränktem Zugriff würde diesen Zweck zunichte machen. Im vorangehenden Skelett Code ist `exposedVar` `Public` und macht `privateClass` für Code verfügbar, der keinen Zugriff auf die Datei haben sollte.  
  
 **Fehler-ID:** BC30909  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Ändern Sie die Zugriffsebene der Variablen, des Prozedur Parameters oder der Funktions Rückgabe so, dass Sie mindestens so restriktiv ist wie die Zugriffsebene des Datentyps.  
  
## <a name="see-also"></a>Siehe auch

- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
