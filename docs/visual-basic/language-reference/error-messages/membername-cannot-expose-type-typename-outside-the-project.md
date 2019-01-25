---
title: '&#39;&lt;Membername&gt; &#39; kann nicht verfügbar machen &#39; &lt;Typename&gt; &#39; außerhalb des Projekts durch &lt;Hiermit&gt; &#39; &lt;Containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 39d316aca5ec306de4b1e43e2eb2d1495f5525d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672343"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39;&lt;Membername&gt; &#39; kann nicht verfügbar machen &#39; &lt;Typename&gt; &#39; außerhalb des Projekts durch &lt;Hiermit&gt; &#39; &lt;Containertypename&gt;&#39;
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
