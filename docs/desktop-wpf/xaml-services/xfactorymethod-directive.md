---
title: x:FactoryMethod-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432785"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod-Anweisung
Gibt eine andere Methode als einen Konstruktor an, die ein XAML-Prozessor verwenden soll, um ein Objekt nach dem Auflösen seines Sicherungstyps zu initialisieren.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML-Attributverwendung, keine x:Argumente  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML-Attributverwendung, x:Argumente als Element(e)  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`methodname`|Der Zeichenfolgenmethodenname einer Methode, die XAML-Prozessoren `object`aufrufen, um die als angegebene Instanz zu initialisieren. Siehe Hinweise.|  
|`oneOrMoreObjectElements`|Ein oder mehrere Objektelemente für Objekte, die Factorymethodenparameter angeben. Ordnung ist bedeutend; Sie gibt die Reihenfolge an, in der Argumente an die Factory-Methode übergeben werden sollen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn `methodname` es sich um eine Instanzmethode handelt, kann sie nicht qualifiziert werden.  
  
 Statische Methoden als Factorymethoden werden unterstützt. Wenn `methodname` es sich `methodname` um eine `typeName.methodName` statische Methode `typeName` handelt, wird als Kombination bereitgestellt, wobei die Klasse, die die statische Factorymethode definiert, benennt wird. `typeName`kann präfix-qualifiziert sein, wenn auf einen Typ in einem zugeordneten xmlns verwiesen wird. `typeName`kann ein anderer `typeof(object)`Typ als sein.  
  
 Die Factorymethode muss eine deklarierte öffentliche Methode des Typs sein, der das relevante Objektelement unterstützt.  
  
 Die Factorymethode muss eine Instanz zurückgeben, die dem relevanten Objekt zugewiesen werden kann. Factory-Methoden sollten niemals null zurückgeben.  
  
 `x:Arguments`arbeitet nach dem Prinzip der besten Übereinstimmung für Die Signaturen von Fabrikmethoden. Beim Matching wird zuerst die Parameteranzahl ausgewertet. Wenn es mehr als eine mögliche Übereinstimmung für eine Parameteranzahl gibt, wird der Parametertyp ausgewertet und die beste Übereinstimmung ermittelt. Wenn nach dieser Phase der Evaluierung immer noch Mehrdeutigkeit enden ist, ist das XAML-Prozessorverhalten nicht definiert.  
  
 Die `x:FactoryMethod` Elementverwendung ist keine Eigenschaftselementverwendung im typischen Sinne, da das Direktivenmarkup nicht auf den Typ des enthaltenden Objektelements verweist. Es wird erwartet, dass die Elementverwendung seltener ist als die Attributverwendung. `x:Arguments`(entweder Attribut- oder Elementverwendung) `x:FactoryMethod` kann zusammen mit der Elementverwendung verwendet werden, dies wird jedoch nicht speziell in den Abschnitten Verwendung angezeigt.  
  
 `x:FactoryMethod`als Element muss vor allen anderen Eigenschaftselementen, `x:Arguments` muss vor allen auch als Elemente zur Verfügung gestellten und muss vor jedem Inhalt / inneren Text / Initialisierung Text vor.  
  
## <a name="see-also"></a>Weitere Informationen

- [x:Arguments-Anweisung](xarguments-directive.md)
