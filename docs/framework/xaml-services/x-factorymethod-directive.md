---
title: x:FactoryMethod-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 75225e624abdd3dc0862a04fae409da48b3f0d1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563414"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod-Anweisung
Gibt eine Methode als einen Konstruktor, den ein XAML-Prozessor verwenden soll, um ein Objekt nach seiner Unterstützungstyp auflösen zu initialisieren.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>Verwendung von XAML-Attributen, keine X: Arguments  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>Verwendung von XAML-Attributen, X: Arguments als Element(e)  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`methodname`|Die Methode Zeichenfolgennamen einer Methode, die XAML-Prozessoren zum Initialisieren der Instanz aufrufen als angegeben `object`. Siehe Hinweise.|  
|`oneOrMoreObjectElements`|Ein oder mehrere Objektelemente für Objekte, die Parameter der Factory-Methode angeben. Die Reihenfolge ist wichtig; Es gibt an, die Reihenfolge, in der Argumente an die Factory-Methode übergeben werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `methodname` ist eine Instanzmethode kann nicht qualifiziert sein.  
  
 Statische Methoden als Factorymethoden werden unterstützt. Wenn `methodname` ist eine statische Methode `methodname` dient als ein *TypeName*. *Methodenname* zusammen, auf dem *TypeName* benennt die Klasse, die die statische Factorymethode definiert. *TypeName* Präfix qualifiziert sein, wenn auf einen Typ in einem zugeordneten Xmlns verweisen kann. *TypeName* kann ein anderen Typ als `typeof(``object``)`.  
  
 Die Factory-Methode muss eine deklarierte öffentliche Methode des Typs, der die relevante Objektelement unterstützt.  
  
 Die Factory-Methode muss es sich um eine Instanz zurückgeben, die auf das entsprechende Objekt zugeordnet ist. Factorymethoden sollten nie null zurückgeben.  
  
 `x:Arguments` Ein Prinzip der beste Übereinstimmung für Signaturen von Factorymethoden verarbeitet. Die Parameteranzahl Abgleich zuerst ausgewertet. Gibt es ist mehr als eine mögliche Entsprechung für ein Parameteranzahl, Parametertyp ausgewertet und die beste Übereinstimmung ermittelt wird. Wenn Mehrdeutigkeiten nach dieser Phase der Auswertung immer noch vorhanden ist, ist die XAML-Prozessorverhalten nicht definiert.  
  
 Die `x:FactoryMethod` Elementverwendung ist nicht Eigenschaftenelementen insofern typisch, da die Richtlinie Markup nicht des enthaltenden Objektelements Typ verweist. Es wird davon ausgegangen, dass Elementverwendung ist weniger gebräuchlich als Attributen. `x:Arguments` (Attribut- oder Elementwert Verwendung) verwendet werden kann, zusammen mit `x:FactoryMethod` Elementverwendung, aber dies wird nicht ausdrücklich angezeigt in den Abschnitten.  
  
 `x:FactoryMethod` wie ein Element alle anderen Eigenschaftenelemente vorangestellt werden muss, müssen alle vorausgehen `x:Arguments` auch als Elemente angegeben und muss alle Inhalte bzw. innere Text/Initialisierungstext vorangehen.  
  
## <a name="see-also"></a>Siehe auch  
 [x:Arguments-Direktive](../../../docs/framework/xaml-services/x-arguments-directive.md)
