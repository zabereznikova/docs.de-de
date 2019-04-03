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
ms.openlocfilehash: d8f2f16d2fb15f2e840f13f177d3fea83fda315e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843100"
---
# <a name="access-levels-in-visual-basic"></a>Zugriffsebenen in Visual Basic
Die *Zugriffsebene* eines deklarierten Elements wird das Ausmaß der Fähigkeit, darauf zuzugreifen, d. h., welcher Code hat über die Berechtigung zum Lesen oder darin schreiben. Dies wird bestimmt, nicht nur durch, wie Sie das Element selbst deklarieren, sondern auch von der Zugriffsebene des Containers von des Elements. Code, der nicht auf ein einschließenden Element zugreifen kann: Dabei kann auf keinen der enthaltenen Elemente zugreifen, auch wenn diese als deklariert `Public`. Z. B. eine `Public` -Variable in eine `Private` Struktur kann aus zugegriffen werden, in der Klasse, die die Struktur enthält, jedoch nicht von außerhalb der Klasse.  
  
## <a name="public"></a>Public  
 Die [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element zugegriffen werden kann, von Code an einer beliebigen Stelle im selben Projekt, aus anderen Projekten, die auf das Projekt zu verweisen und einer Assembly, die aus dem Projekt erstellt. Der folgende Code zeigt ein Beispiel für `Public` Deklaration.  
  
```vb  
Public Class classForEverybody  
```  
  
 Sie können `Public` nur auf Modul, Schnittstelle oder Namespace-Ebene. Dies bedeutet, dass Sie ein öffentliches Element auf der Ebene einer Quelldatei oder-Namespace oder in einer Schnittstelle, Modul, Klasse oder Struktur, aber nicht in einer Prozedur deklarieren.  
  
## <a name="protected"></a>Protected  
 Die [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element nur von innerhalb der gleichen Klasse oder aus einer von dieser Klasse abgeleiteten Klasse zugegriffen werden kann. Der folgende Code zeigt ein Beispiel für `Protected` Deklaration.  
  
```vb  
Protected Class classForMyHeirs  
```  
  
 Sie können `Protected` nur zur Klasse Ebene aus, und nur wenn Sie einen Member Deklarieren einer Klasse. Dies bedeutet, dass Sie ein geschütztes Element in einer Klasse, aber nicht auf der Ebene einer Quelldatei oder einen Namespace oder in einer Schnittstelle, Modul, Struktur oder Prozedur deklarieren.  
  
## <a name="friend"></a>Friend  
 Die [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element in der gleichen Assembly, jedoch nicht aus erreichbar ist außerhalb der Assembly. Der folgende Code zeigt ein Beispiel für `Friend` Deklaration.  
  
```vb  
Friend stringForThisProject As String  
```  
  
 Sie können `Friend` nur auf Modul, Schnittstelle oder Namespace-Ebene. Dies bedeutet, dass Sie eine Friend-Element auf der Ebene einer Quelldatei oder-Namespace oder in einer Schnittstelle, Modul, Klasse oder Struktur, aber nicht in einer Prozedur deklarieren.  
  
## <a name="protected-friend"></a>Protected Friend  
 Die [Protected Friend](../../../language-reference/modifiers/protected-friend.md) schlüsselwortkombination in der deklarationsanweisung gibt an, dass das Element kann oder von abgeleiteten Klassen als auch innerhalb zugegriffen werden der gleichen Assembly oder beides. Der folgende Code zeigt ein Beispiel für `Protected Friend` Deklaration.  
  
```vb  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 Sie können `Protected Friend` nur zur Klasse Ebene aus, und nur wenn Sie einen Member Deklarieren einer Klasse. Dies bedeutet, dass Sie ein geschütztes Friend-Element in einer Klasse, aber nicht auf der Ebene einer Quelldatei oder einen Namespace oder in einer Schnittstelle, Modul, Struktur oder Prozedur deklarieren.  
  
## <a name="private"></a>Private  
 Die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der deklarationsanweisung gibt an, dass das Element nur von innerhalb des gleichen Moduls, Klasse oder Struktur zugegriffen werden kann. Der folgende Code zeigt ein Beispiel für `Private` Deklaration.  
  
```vb  
Private numberForMeOnly As Integer  
```  
  
 Sie können `Private` nur auf Modulebene verwenden. Dies bedeutet, dass Sie ein privates Element in einem Modul, Klasse oder Struktur, aber nicht auf der Ebene der Quelldateien oder -Namespace, in einer Schnittstelle oder in einer Prozedur deklarieren.  
  
 Klicken Sie auf der Modulebene der `Dim` Anweisung ohne Schlüsselwörter Ebene entspricht einer `Private` Deklaration. Allerdings möchten Sie verwenden die `Private` Schlüsselwort, um Ihr Code leichter zu lesen und interpretieren.  

## <a name="private-protected"></a>Privat geschützt

Die [Private Protected](../../../language-reference/modifiers/private-protected.md) schlüsselwortkombination in der deklarationsanweisung gibt an, dass das Element nur von innerhalb der gleichen Klasse sowie von abgeleiteten Klassen finden Sie in der gleichen Assembly wie die enthaltende Klasse zugegriffen werden kann. Die `Private Protected` Zugriffsmodifizierer ist ab Visual Basic 15.5 unterstützt.

Das folgende Beispiel zeigt eine `Private Protected` Deklaration:

```vb
Private Protected internalValue As Integer
```

Sie können deklarieren, ein `Private Protected` Element nur innerhalb einer Klasse. Es kann nicht innerhalb einer Schnittstelle oder Struktur deklariert, noch können Sie Sie deklarieren auf der Ebene der Quelldateien oder -Namespace, in einer Schnittstelle oder eine Struktur oder in einer Prozedur.

Die `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15.5 und höher unterstützt. Um es zu verwenden, fügen Sie Ihrer Visual Basic-Projektdatei (*.vbproj) das folgende Element hinzu. Solange Visual Basic 15.5 oder höher auf Ihrem System installiert ist, können dass Sie alle der Features von Programmiersprachen unterstützt werden, indem Sie die neueste Version von Visual Basic-Compiler nutzen:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Verwenden der `Private Protected` Zugriffsmodifizierer, müssen Sie Ihre Visual Basic-Projektdatei (*.vbproj) das folgende Element hinzufügen:

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [Festlegen der Sprache Visual Basic-Version](../../../language-reference/configure-language-version.md).

## <a name="access-modifiers"></a>Zugriffsmodifizierer  

Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Die folgende Tabelle vergleicht die Zugriffsmodifizierer.  
  
|Zugriffsmodifizierer|Gewährte Zugriffsebene|Elemente können Sie mit dieser Zugriffsebene deklarieren.|Deklarationskontext, in dem dieser Modifizierer verwendet werden können|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|Unrestricted:<br /><br /> Jeglicher Code, der ein öffentliches Element sehen kann darauf zugreifen.|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Interface<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected`|Derivational:<br /><br /> Programmieren Sie in der Klasse, die deklariert, dass ein geschütztes Element oder einer Klasse abgeleitet ist, auf das Element zugreifen können|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Friend`|Assembly:<br /><br /> Programmieren Sie in der Assembly, die deklariert, dass ein Friend-Element, die darauf zugreifen können|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Interface<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|  
|`Protected` `Friend`|Der Union `Protected` und `Friend`:<br /><br /> Programmieren Sie in der gleichen Klasse oder derselben Assembly als protected Friend-Element oder innerhalb einer Klasse, die von der Elements-Klasse abgeleitet wurde, können sie darauf zugreifen|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|  
|`Private`|Deklarationskontext:<br /><br /> Code in den Typ, der ein privates Element einschließlich Code innerhalb von enthaltenen Typen deklariert, kann das Element zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Modul<br /><br /> Klasse<br /><br /> Struktur|
|`Private Protected`|Code in der Klasse, die ein privates geschütztes Element deklariert, oder Code in einer abgeleiteten Klasse finden Sie in der gleichen Assembly wie die Bas-Klasse.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Membervariablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|
  
## <a name="see-also"></a>Siehe auch

- [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Vorgehensweise: Steuern der Verfügbarkeit einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)
- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
