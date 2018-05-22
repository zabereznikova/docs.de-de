---
title: Zugriffsebenen in Visual Basic
ms.date: 05/10/2018
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private Protected access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
ms.openlocfilehash: 1e2d43f33a352d3f4502965c5368eb901e7bffdf
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="access-levels-in-visual-basic"></a>Zugriffsebenen in Visual Basic
Die *Zugriffsebene* eines deklarierten Elements wird das Ausmaß der die Möglichkeit für den Zugriff darauf, welcher Code hat, also über die Berechtigung zum Lesen oder darin schreiben. Dies wird nicht nur durch, wie Sie das Element selbst deklarieren, sondern auch die Zugriffsebene des Containers des Elements bestimmt. Code, der ein einschließenden Element zugreifen kann zugreifen der enthaltenen Elemente, auch wenn diese als deklariert `Public`. Z. B. eine `Public` -Variable in eine `Private` Struktur kann aus zugegriffen werden, in der Klasse, die die Struktur enthält, jedoch nicht von außerhalb dieser Klasse.  
  
## <a name="public"></a>Public  
 Die [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element zugegriffen werden kann, aus Code an einer beliebigen Stelle im selben Projekt als andere Projekte, die auf das Projekt zu verweisen und von einer Assembly aus dem Projekt erstellt. Der folgende Code zeigt ein Beispiel für `Public` Deklaration.  
  
```vb  
Public Class classForEverybody  
```  
  
 Sie können `Public` nur auf Modul, Schnittstelle oder Namespace-Ebene. Dies bedeutet, dass Sie ein öffentliches Element auf der Ebene einer Quelldatei oder-Namespace oder in einer Schnittstelle, Modul, Klasse oder Struktur, aber nicht in einer Prozedur deklarieren können.  
  
## <a name="protected"></a>Protected  
 Die [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element innerhalb der gleichen Klasse oder aus einer Klasse, die von dieser Klasse abgeleiteten nur aus zugegriffen werden kann. Der folgende Code zeigt ein Beispiel für `Protected` Deklaration.  
  
```vb  
Protected Class classForMyHeirs  
```  
  
 Sie können `Protected` nur auf Ebene, und nur wenn Sie deklarieren einen Member einer Klasse. Dies bedeutet, dass Sie ein geschütztes Element in einer Klasse, aber nicht auf der Ebene einer Quelldatei oder Namespace oder in einer Schnittstelle, Modul, Struktur oder Prozedur deklarieren können.  
  
## <a name="friend"></a>Friend  
 Die ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) -Schlüsselwort in der deklarationsanweisung fest, dass das Element aus kann innerhalb derselben Assembly, jedoch nicht von zugegriffen werden außerhalb der Assembly. Der folgende Code zeigt ein Beispiel für `Friend` Deklaration.  
  
```vb  
Friend stringForThisProject As String  
```  
  
 Sie können `Friend` nur auf Modul, Schnittstelle oder Namespace-Ebene. Dies bedeutet, dass Sie eine Friend-Element auf der Ebene einer Quelldatei oder-Namespace oder in einer Schnittstelle, Modul, Klasse oder Struktur, aber nicht in einer Prozedur deklarieren können.  
  
## <a name="protected-friend"></a>Protected Friend  
 Die `Protected` und `Friend` Schlüsselwörter, die zusammen in der deklarationsanweisung angeben, dass das Element von abgeleiteten Klassen oder aus zugegriffen werden kann der gleichen Assembly oder beides. Der folgende Code zeigt ein Beispiel für `Protected Friend` Deklaration.  
  
```vb  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 Sie können `Protected Friend` nur auf Ebene, und nur wenn Sie deklarieren einen Member einer Klasse. Dies bedeutet, dass Sie ein geschütztes Friend-Element in einer Klasse, aber nicht auf der Ebene einer Quelldatei oder Namespace oder in einer Schnittstelle, Modul, Struktur oder Prozedur deklarieren können.  
  
## <a name="private"></a>Private  
 Die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element innerhalb des gleichen Moduls, Klasse oder Struktur nur aus zugegriffen werden kann. Der folgende Code zeigt ein Beispiel für `Private` Deklaration.  
  
```vb  
Private numberForMeOnly As Integer  
```  
  
 Sie können `Private` nur auf Modulebene verwenden. Dies bedeutet, dass Sie ein privates Element innerhalb eines Moduls, eine Klasse oder eine Struktur, aber nicht auf das Maß an einer Quelldatei oder eines Namespaces, die innerhalb einer Schnittstelle oder in einer Prozedur deklarieren können.  
  
 Klicken Sie auf der Modulebene der `Dim` -Anweisung ohne Zugriffsebenen-Schlüsselwörter ist gleichbedeutend mit einer `Private` Deklaration. Allerdings kann es sinnvoll sein, verwenden Sie die `Private` Schlüsselwort, um die Lesbarkeit Ihres Codes erschweren einfacher zu lesen und zu interpretieren.  

## <a name="private-protected"></a>Geschützt privat

Die [Private geschützte](../../../language-reference/modifiers/private-protected.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element innerhalb der gleichen Klasse sowie von abgeleiteten Klassen aus derselben Assembly wie die enthaltende Klasse nur aus zugegriffen werden kann. Die `Private Protected` Zugriffsmodifizierer wird beginnend mit Visual Basic 15.5 unterstützt.

Das folgende Beispiel zeigt eine `Private Protected` Deklaration:

```vb
Private Protected internalValue As Integer
```

Sie können Deklarieren einer `Private Protected` Element nur innerhalb einer Klasse. Es kann nicht innerhalb einer Schnittstelle oder Struktur deklariert, noch können Sie deklarieren Sie es auf der Ebene einer Quelldatei oder in einer Schnittstelle oder eine Struktur oder in einer Prozedur-Namespace.

Die `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15.5 und höher unterstützt. Um es zu verwenden, fügen Sie das folgende Element der Visual Basic-Projektdatei (*.vbproj). Wie lange wie Visual Basic 15.5 oder höher auf Ihrem System installiert ist, können sie alle von der neuesten Version von Visual Basic-Compiler unterstützt Sprachfunktionen zu nutzen:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Verwenden der `Private Protected` Zugriffsmodifizierer, müssen Sie das folgende Element hinzufügen, der Visual Basic-Projektdatei (*.vbproj):

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

 ## <a name="access-modifiers"></a>Zugriffsmodifizierer  
 Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Die folgende Tabelle vergleicht die Zugriffsmodifizierern.  
  
|Zugriffsmodifizierer|Gewährte Zugriffsebene|Elemente können Sie mit dieser Zugriffsebene deklarieren.|Deklarationskontext, anhand derer Sie this-Modifizierer verwenden können|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|Nicht eingeschränkt:<br /><br /> Jeglicher Code, der ein öffentliches Element sehen kann, die darauf zugreifen können|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Interface<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected`|Ableitungsschritte:<br /><br /> Code in der Klasse, die deklariert, dass ein geschütztes Element oder eine daraus abgeleitete Klasse das Element zugreifen können|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Friend`|Assembly:<br /><br /> Code in der Assembly, die deklariert, dass ein Element "Friend" darauf zugreifen können|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Interface<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected` `Friend`|Der Union `Protected` und `Friend`:<br /><br /> Code in derselben Klasse oder der gleichen Assembly als protected Friend-Element oder innerhalb einer Klasse, die die Element-Klasse abgeleitet, die darauf zugreifen können|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Private`|Deklarationskontext:<br /><br /> Code in den Typ, der ein privates Element, einschließlich Code innerhalb von enthaltenen Typen deklariert kann das Element zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Modul<br /><br /> Klasse<br /><br /> Struktur|
|`Private Protected`|Code in der Klasse, die ein privates geschütztes Element deklariert, oder Code in einer abgeleiteten Klasse, die der gleichen Assembly wie die Bas-Klasse.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|
  
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
