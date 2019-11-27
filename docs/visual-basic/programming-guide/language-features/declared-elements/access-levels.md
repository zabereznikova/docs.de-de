---
title: Zugriffsebenen
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
ms.openlocfilehash: 33a218a2acc3c876428d6c9a887280a559f84323
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348681"
---
# <a name="access-levels-in-visual-basic"></a>Zugriffsebenen in Visual Basic

Die *Zugriffsebene* eines deklarierten Elements ist der Umfang der Möglichkeit, darauf zuzugreifen, d. h., welcher Code über die Berechtigung zum Lesen oder schreiben verfügt. Dies wird nicht nur durch die Art und Weise bestimmt, wie Sie das Element selbst deklarieren, sondern auch durch die Zugriffsebene des Containers des Elements. Code, der nicht auf ein enthaltende Element zugreifen kann, kann nicht auf seine enthaltenen Elemente zugreifen, auch auf die als `Public`deklarierten Elemente. Beispielsweise kann auf eine `Public` Variable in einer `Private` Struktur von innerhalb der Klasse zugegriffen werden, die die Struktur enthält, jedoch nicht von außerhalb der Klasse.

## <a name="public"></a>Öffentlich

Das [Public](../../../language-reference/modifiers/public.md) -Schlüsselwort in der Deklarations Anweisung gibt an, dass der Zugriff auf das Element von Code an einer beliebigen Stelle im gleichen Projekt, aus anderen Projekten, die auf das Projekt verweisen, und aus allen aus dem Projekt erstellten Assemblys möglich ist Der folgende Code zeigt eine Beispiel `Public` Deklaration:

```vb
Public Class ClassForEverybody
```

Sie können `Public` nur auf der Ebene "Module", "Interface" oder "Namespace" verwenden. Dies bedeutet, dass Sie ein öffentliches Element auf der Ebene einer Quelldatei oder eines Namespaces oder innerhalb einer Schnittstelle, eines Moduls, einer Klasse oder einer Struktur, aber nicht in einer Prozedur deklarieren können.
  
## <a name="protected"></a>Protected

Das [Protected](../../../language-reference/modifiers/protected.md) -Schlüsselwort in der Deklarations Anweisung gibt an, dass auf das Element nur innerhalb derselben Klasse oder einer von dieser Klasse abgeleiteten Klasse zugegriffen werden kann. Der folgende Code zeigt eine Beispiel `Protected` Deklaration:

```vb
Protected Class ClassForMyHeirs
```

Sie können `Protected` nur auf Klassenebene und nur dann verwenden, wenn Sie einen Member einer Klasse deklarieren. Dies bedeutet, dass Sie ein geschütztes Element in einer Klasse, jedoch nicht auf der Ebene einer Quelldatei oder eines Namespaces oder innerhalb einer Schnittstelle, eines Moduls, einer Struktur oder einer Prozedur deklarieren können.

## <a name="friend"></a>Friend

Das [Friend](../../../language-reference/modifiers/friend.md) -Schlüsselwort in der Deklarations Anweisung gibt an, dass der Zugriff auf das Element innerhalb der gleichen Assembly, jedoch nicht von außerhalb der Assembly möglich ist. Der folgende Code zeigt eine Beispiel `Friend` Deklaration:

```vb
Friend stringForThisProject As String
```

Sie können `Friend` nur auf der Ebene "Module", "Interface" oder "Namespace" verwenden. Dies bedeutet, dass Sie ein Friend-Element auf der Ebene einer Quelldatei oder eines Namespaces oder innerhalb einer Schnittstelle, eines Moduls, einer Klasse oder einer Struktur, aber nicht in einer Prozedur deklarieren können.

## <a name="protected-friend"></a>Protected Friend

Die Kombination aus [geschütztem Friend](../../../language-reference/modifiers/protected-friend.md) -Schlüsselwort in der Deklarations Anweisung gibt an, dass auf das Element entweder von abgeleiteten Klassen oder innerhalb derselben Assembly oder von beidem aus zugegriffen werden kann. Der folgende Code zeigt eine Beispiel `Protected Friend` Deklaration:

```vb
Protected Friend stringForProjectAndHeirs As String
```

Sie können `Protected Friend` nur auf Klassenebene und nur dann verwenden, wenn Sie einen Member einer Klasse deklarieren. Dies bedeutet, dass Sie ein geschütztes Friend-Element in einer Klasse, jedoch nicht auf der Ebene einer Quelldatei oder eines Namespaces oder innerhalb einer Schnittstelle, eines Moduls, einer Struktur oder einer Prozedur deklarieren können.

## <a name="private"></a>Privat

Das [private](../../../language-reference/modifiers/private.md) -Schlüsselwort in der Deklarations Anweisung gibt an, dass auf das Element nur innerhalb desselben Moduls, einer Klasse oder Struktur zugegriffen werden kann. Der folgende Code zeigt eine Beispiel `Private` Deklaration:

```vb
Private _numberForMeOnly As Integer
```

Sie können `Private` nur auf Modulebene verwenden. Dies bedeutet, dass Sie ein privates Element innerhalb eines Moduls, einer Klasse oder einer Struktur, aber nicht auf der Ebene einer Quelldatei oder eines Namespaces innerhalb einer Schnittstelle oder in einer Prozedur deklarieren können.

Auf Modulebene entspricht die `Dim`-Anweisung ohne Zugriffsebenen-Schlüsselwörter einer `Private` Deklaration. Möglicherweise möchten Sie jedoch das `Private`-Schlüsselwort verwenden, um den Code einfacher zu lesen und zu interpretieren.

## <a name="private-protected"></a>Private Protected

Die Kombination aus [privatem geschütztem](../../../language-reference/modifiers/private-protected.md) Schlüsselwort in der Deklarations Anweisung gibt an, dass auf das Element nur innerhalb derselben Klasse und von abgeleiteten Klassen zugegriffen werden kann, die in derselben Assembly wie die enthaltende Klasse gefunden werden. Der `Private Protected` Zugriffsmodifizierer wird ab Visual Basic 15,5 unterstützt.

Das folgende Beispiel zeigt eine `Private Protected` Deklaration:

```vb
Private Protected internalValue As Integer
```

Sie können ein `Private Protected`-Element nur innerhalb einer Klasse deklarieren. Sie können Sie nicht in einer Schnittstelle oder Struktur deklarieren, und Sie können Sie auch nicht auf der Ebene einer Quelldatei oder eines Namespaces, innerhalb einer Schnittstelle oder Struktur oder in einer Prozedur deklarieren.

Der `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15,5 und höher unterstützt. Um es zu verwenden, fügen Sie das folgende-Element zu Ihrer Visual Basic Project-Datei ( *\*. vbproj*) hinzu. Solange Visual Basic 15,5 oder höher auf Ihrem System installiert ist, können Sie alle sprach Features nutzen, die von der neuesten Version des Visual Basic Compilers unterstützt werden:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Um den `Private Protected` Zugriffsmodifizierer zu verwenden, müssen Sie das folgende-Element in der Visual Basic Projektdatei ( *\*. vbproj*) hinzufügen:

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie [unter Festlegen der Visual Basic Sprachversion](../../../language-reference/configure-language-version.md).

## <a name="access-modifiers"></a>Zugriffsmodifizierer

Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Die folgende Tabelle vergleicht die Zugriffsmodifizierer:

|Access-Modifizierer|Gewährte Zugriffsebene|Elemente, die Sie mit dieser Zugriffsebene deklarieren können|Der Deklarations Kontext, in dem Sie diesen Modifizierer verwenden können.|
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|
|`Public`|Unbegrenzt<br /><br /> Sämtlicher Code, der ein öffentliches Element sehen kann, kann darauf zugreifen.|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Element Variablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Schnittstelle<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|
|`Protected`|Derivational:<br /><br /> Der Code in der Klasse, die ein geschütztes Element deklariert, oder eine Klasse, die davon abgeleitet ist, kann auf das Element zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Element Variablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|
|`Friend`|Assembly:<br /><br /> Der Code in der Assembly, die ein Friend-Element deklariert, kann darauf zugreifen.|Schnittstellen<br /><br /> Module<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Element Variablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Quelldatei<br /><br /> Namespace<br /><br /> Schnittstelle<br /><br /> Modul<br /><br /> Klasse<br /><br /> Struktur|
|`Protected` `Friend`|Union of `Protected` und `Friend`:<br /><br /> Code in derselben Klasse oder in derselben Assembly wie ein geschütztes Friend-Element oder in einer Klasse, die von der Klasse des Elements abgeleitet ist, kann darauf zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Element Variablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|
|`Private`|Deklarations Kontext:<br /><br /> Code in dem Typ, der ein privates Element deklariert, einschließlich Code in enthaltenen Typen, kann auf das Element zugreifen.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Strukturmember<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Element Variablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Modul<br /><br /> Klasse<br /><br /> Struktur|
|`Private Protected`|Code in der-Klasse, die ein privates geschütztes Element deklariert, oder Code in einer abgeleiteten Klasse, der sich in derselben Assembly wie die BAS-Klasse befindet.|Schnittstellen<br /><br /> Klassen<br /><br /> Strukturen<br /><br /> Verfahren<br /><br /> Eigenschaften<br /><br /> Element Variablen<br /><br /> Konstanten<br /><br /> Enumerationen<br /><br /> Ereignisse<br /><br /> Externe Deklarationen<br /><br /> Delegaten|Klasse|

## <a name="see-also"></a>Siehe auch

- [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)
- [Static](../../../language-reference/modifiers/static.md)
- [Namen deklarierter Elemente](declared-element-names.md)
- [Verweise auf deklarierte Elemente](references-to-declared-elements.md)
- [Merkmale deklarierter Elemente](declared-element-characteristics.md)
- [Lebensdauer in Visual Basic](lifetime.md)
- [Bereich in Visual Basic](scope.md)
- [Gewusst wie: Steuern der Verfügbarkeit einer Variablen](how-to-control-the-availability-of-a-variable.md)
- [Variablen](../variables/index.md)
- [Variablendeklaration](../variables/variable-declaration.md)
