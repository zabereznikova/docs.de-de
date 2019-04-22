---
title: <membername> kann den <typename>-Typ nicht außerhalb des Projekts über <containertype> "<containertypename>" verfügbar machen.
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 16f579a05236ba8977a071cb08068be8e98799f8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818339"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>'\<Membername >' kann nicht verfügbar machen "\<Typname >' außerhalb des Projekts durch \<Hiermit > '\<Containertypename >'
Eine Variable, Parameter der Prozedur oder Funktion zurückgegeben wird außerhalb des Containers verfügbar gemacht, aber sie wird deklariert, als Typ, der außerhalb des Containers nicht verfügbar gemacht werden muss.  
  
 Das folgende Codegerüst zeigt eine Situation, die diesen Fehler generiert.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Ein Typ, der deklariert wird `Protected`, `Friend`, `Protected Friend`, oder `Private` außerhalb der Deklarationskontext eingeschränkten Zugriff haben soll. Verwenden sie, wie die Daten widerspricht Typ einer Variablen mit weniger eingeschränktem Zugriff diesen Zweck. Im vorangehenden Code Skelett `exposedVar` ist `Public` und macht `privateClass` an Code, der keinen Zugriff darauf haben sollten.  
  
 **Fehler-ID:** BC30909  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ändern Sie die Zugriffsebene der Variablen, Parameter der Prozedur oder Funktion zurückkehren, um die mindestens so restriktiv als die Zugriffsebene seines Datentyps sein.  
  
## <a name="see-also"></a>Siehe auch

- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
