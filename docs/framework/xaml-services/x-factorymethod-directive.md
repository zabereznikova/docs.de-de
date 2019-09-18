---
title: x:FactoryMethod-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 586965dd4094e81fd830a09b64604cf33f195630
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053777"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod-Anweisung
Gibt eine andere Methode als einen Konstruktor an, der von einem XAML-Prozessor zum Initialisieren eines Objekts nach der Auflösung des Unterstützungs Typs verwendet werden soll.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Verwendung von XAML-Attributen, keine x:Arguments  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Verwendung von XAML-Attributen, x:Arguments als Element (e)  
  
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
|`methodname`|Der Name der Zeichen folgen Methode einer Methode, die XAML-Prozessoren aufruft, um die Instanz `object`zu initialisieren, die als angegeben wird. Siehe Hinweise.|  
|`oneOrMoreObjectElements`|Ein oder mehrere Objekt Elemente für-Objekte, die factorymethodenparameter angeben. Die Reihenfolge ist wichtig. Sie gibt die Reihenfolge an, in der Argumente an die Factorymethode geleitet werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `methodname` eine Instanzmethode ist, kann Sie nicht qualifiziert werden.  
  
 Statische Methoden als Factorymethoden werden unterstützt. Wenn `methodname` eine statische Methode ist, `methodname` wird als *Typname*bereitgestellt. *MethodName* -Kombination, wobei *tykame* die Klasse benennt, die die statische Factorymethode definiert. *Typname* kann als Präfix qualifiziert werden, wenn auf einen Typ in einem zugeordneten xmlns verwiesen wird. *Typname* kann ein anderer Typ sein als `typeof(object)`.  
  
 Die Factorymethode muss eine deklarierte öffentliche Methode des Typs sein, der das relevante Objekt Element unterstützt.  
  
 Die Factorymethode muss eine Instanz zurückgeben, die dem relevanten Objekt zugewiesen werden kann. Factorymethoden sollten niemals NULL zurückgeben.  
  
 `x:Arguments`arbeitet mit einem Prinzip der besten Entsprechung für Signaturen von Factorymethoden. Bei der Übereinstimmung wird die Parameter Anzahl zuerst ausgewertet. Wenn mehr als eine mögliche Entsprechung für eine Parameter Anzahl vorhanden ist, wird der Parametertyp ausgewertet und die beste Entsprechung festgelegt. Wenn nach dieser Evaluierungsphase immer noch Mehrdeutigkeit vorliegt, ist das XAML-Prozessor Verhalten nicht definiert.  
  
 Die `x:FactoryMethod` Element Verwendung ist im typischen Sinn nicht die Verwendung von Eigenschafts Elementen, da das direktivenmarkup nicht auf den Typ des enthaltenden Objekt Elements verweist. Es wird erwartet, dass die Element Verwendung weniger häufig ist als die Attribut Verwendung. `x:Arguments`(entweder Attribut-oder Element Verwendung) kann zusammen mit der `x:FactoryMethod` Verwendung von Elementen verwendet werden, dies wird jedoch nicht speziell in den Verwendungs Abschnitten veranschaulicht.  
  
 `x:FactoryMethod`Da ein Element vor allen anderen Eigenschaften Elementen stehen muss, muss vor allen `x:Arguments` Elementen stehen, die ebenfalls als-Elemente bereitgestellt werden, und vor jedem Text-/InnerText-/Initialisierungstext stehen muss.  
  
## <a name="see-also"></a>Siehe auch

- [x:Arguments-Direktive](x-arguments-directive.md)
