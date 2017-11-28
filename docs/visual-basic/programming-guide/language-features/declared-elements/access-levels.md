---
title: Zugriffsebenen in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 87e43ac7e813cece1179bdaf24c86fa62adcb438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="access-levels-in-visual-basic"></a>Zugriffsebenen in Visual Basic
Die *Zugriffsebene* eines deklarierten Elements wird das Ausmaß der die Möglichkeit für den Zugriff darauf, welcher Code hat, also über die Berechtigung zum Lesen oder darin schreiben. Dies wird nicht nur durch, wie Sie das Element selbst deklarieren, sondern auch die Zugriffsebene des Containers des Elements bestimmt. Code, der ein einschließenden Element zugreifen kann zugreifen der enthaltenen Elemente, auch wenn diese als deklariert `Public`. Z. B. eine `Public` -Variable in eine `Private` Struktur kann aus zugegriffen werden, in der Klasse, die die Struktur enthält, jedoch nicht von außerhalb dieser Klasse.  
  
## <a name="public"></a>Public  
 Die [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass die Elemente von Code an einer beliebigen Stelle im selben Projekt, aus anderen Projekten, die auf das Projekt zu verweisen und aus beliebigen Assemblys im Projekt erstellten zugegriffen werden können. Der folgende Code zeigt ein Beispiel für `Public` Deklaration.  
  
```  
Public Class classForEverybody  
```  
  
 Sie können `Public` nur auf Modul, Schnittstelle oder Namespace-Ebene. Dies bedeutet, dass Sie ein öffentliches Element auf der Ebene einer Quelldatei oder-Namespace oder in einer Schnittstelle, Modul, Klasse oder Struktur, aber nicht in einer Prozedur deklarieren können.  
  
## <a name="protected"></a>Protected  
 Die [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass die Elemente innerhalb der gleichen Klasse oder aus einer Klasse, die von dieser Klasse abgeleiteten nur aus zugegriffen werden können. Der folgende Code zeigt ein Beispiel für `Protected` Deklaration.  
  
```  
Protected Class classForMyHeirs  
```  
  
 Sie können `Protected` nur auf Ebene, und nur wenn Sie deklarieren einen Member einer Klasse. Dies bedeutet, dass Sie ein geschütztes Element in einer Klasse, aber nicht auf der Ebene einer Quelldatei oder Namespace oder in einer Schnittstelle, Modul, Struktur oder Prozedur deklarieren können.  
  
## <a name="friend"></a>Friend  
 Die ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass die Elemente innerhalb der gleichen Assembly, nicht jedoch aus zugegriffen werden können außerhalb der Assembly. Der folgende Code zeigt ein Beispiel für `Friend` Deklaration.  
  
```  
Friend stringForThisProject As String  
```  
  
 Sie können `Friend` nur auf Modul, Schnittstelle oder Namespace-Ebene. Dies bedeutet, dass Sie eine Friend-Element auf der Ebene einer Quelldatei oder-Namespace oder in einer Schnittstelle, Modul, Klasse oder Struktur, aber nicht in einer Prozedur deklarieren können.  
  
## <a name="protected-friend"></a>Protected Friend  
 Die `Protected` und `Friend` Schlüsselwörter, die zusammen in der deklarationsanweisung angeben, dass die Elemente von abgeleiteten Klassen oder heraus zugegriffen werden können der gleichen Assembly oder beides. Der folgende Code zeigt ein Beispiel für `Protected Friend` Deklaration.  
  
```  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 Sie können `Protected Friend` nur auf Ebene, und nur wenn Sie deklarieren einen Member einer Klasse. Dies bedeutet, dass Sie ein geschütztes Friend-Element in einer Klasse, aber nicht auf der Ebene einer Quelldatei oder Namespace oder in einer Schnittstelle, Modul, Struktur oder Prozedur deklarieren können.  
  
## <a name="private"></a>Private  
 Die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass die Elemente innerhalb des gleichen Moduls, Klasse oder Struktur nur aus zugegriffen werden können. Der folgende Code zeigt ein Beispiel für `Private` Deklaration.  
  
```  
Private numberForMeOnly As Integer  
```  
  
 Sie können `Private` nur auf Modulebene verwenden. Dies bedeutet, dass Sie ein privates Element innerhalb eines Moduls, eine Klasse oder eine Struktur, aber nicht auf das Maß an einer Quelldatei oder eines Namespaces, die innerhalb einer Schnittstelle oder in einer Prozedur deklarieren können.  
  
 Klicken Sie auf der Modulebene der `Dim` -Anweisung ohne Zugriffsebenen-Schlüsselwörter ist gleichbedeutend mit einer `Private` Deklaration. Allerdings kann es sinnvoll sein, verwenden Sie die `Private` Schlüsselwort, um die Lesbarkeit Ihres Codes erschweren einfacher zu lesen und zu interpretieren.  
  
## <a name="access-modifiers"></a>Zugriffsmodifizierer  
 Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Die folgende Tabelle vergleicht die Zugriffsmodifizierern.  
  
|Zugriffsmodifizierer|Gewährte Zugriffsebene|Elemente können Sie mit dieser Zugriffsebene deklarieren.|Deklarationskontext, anhand derer Sie this-Modifizierer verwenden können|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|Nicht eingeschränkt:<br /><br /> Jeglicher Code, der ein öffentliches Element sehen kann, die darauf zugreifen können|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Schnittstelle<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected`|Ableitungsschritte:<br /><br /> Code in der Klasse, die deklariert, dass ein geschütztes Element oder eine daraus abgeleitete Klasse das Element zugreifen können|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Friend`|Assembly:<br /><br /> Code in der Assembly, die deklariert, dass ein Element "Friend" darauf zugreifen können|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Schnittstelle<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected` `Friend`|Der Union `Protected` und `Friend`:<br /><br /> Code in derselben Klasse oder der gleichen Assembly als protected Friend-Element oder innerhalb einer Klasse, die die Element-Klasse abgeleitet, die darauf zugreifen können|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Private`|Deklarationskontext:<br /><br /> Code in den Typ, der ein privates Element, einschließlich Code innerhalb von enthaltenen Typen deklariert kann das Element zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Modul<br /><br /> Klasse<br /><br /> Struktur|  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)  
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Gewusst wie: Steuern der Verfügbarkeit einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
