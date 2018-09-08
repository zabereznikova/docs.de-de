---
title: x:FactoryMethod-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 436caa9b93467dcf2a0763bcc0962a2beb722315
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199660"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod-Anweisung
Gibt eine Methode als einen Konstruktor, den ein XAML-Prozessor verwenden soll, um ein Objekt zu initialisieren, nach dessen Unterstützungstyp auflösen.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML-Attributverwendung, die keine X: Arguments  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML-Attributverwendung, X: Arguments als Elemente  
  
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
|`methodname`|Der Zeichenfolgenname für die Methode einer Methode, die XAML-Prozessoren aufrufen, zum Initialisieren der Instanz, die als `object`. Siehe Hinweise.|  
|`oneOrMoreObjectElements`|Eine oder mehrere Object-Elemente für Objekte, die Parameter der Factory-Methode angeben. Die Reihenfolge ist wichtig; Es gibt an, die Reihenfolge, in der Argumente, die an die Factorymethode übergeben werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `methodname` ist eine Instanzmethode, kann nicht qualifiziert sein.  
  
 Statische Methoden als Factorymethoden werden unterstützt. Wenn `methodname` ist eine statische Methode, `methodname` dient als ein *TypeName*. *MethodName* Kombination aus, in denen *TypeName* benennt die Klasse, die von der statischen Factorymethode definiert. *TypeName* möglich Präfix qualifiziert sein, wenn auf einen Typ in einem zugeordneten Xmlns beziehen. *TypeName* möglich ein anderen Typ als `typeof(object)`.  
  
 Die Factorymethode muss es sich um eine deklarierte öffentliche Methode des Typs sein, die die relevante Objektelement unterstützt.  
  
 Die Factorymethode muss es sich um eine Instanz zurückgeben, die dem entsprechenden Objekt zugewiesen werden kann. Factorymethoden sollte nie null zurückgeben.  
  
 `x:Arguments` Ein Prinzip der beste Übereinstimmung für Signaturen von Factorymethoden verarbeitet. Abgleich wird die Anzahl der Parameter zuerst ausgewertet. Gibt es ist mehr als eine mögliche Entsprechung für einen die Parameteranzahl, Parametertyp und dann ausgewertet und die beste Übereinstimmung bestimmt wird. Wenn Mehrdeutigkeiten nach dieser Phase der Evaluierung noch vorhanden ist, ist die XAML-Prozessor-Verhalten nicht definiert.  
  
 Die `x:FactoryMethod` Objektelementverwendung ist nicht Eigenschaftselementverwendung im typischen Sinn, da das Markup-Direktive nicht der enthaltenden Objekt Typ des Elements verwiesen wird. Es wird davon ausgegangen, dass Elementverwendung wird seltener auf als die Verwendung von Attributen. `x:Arguments` (entweder Attribut- oder Nutzung) kann verwendet werden, zusammen mit `x:FactoryMethod` Verwendung des Elements, aber dies wird nicht speziell angezeigt in den Abschnitten.  
  
 `x:FactoryMethod` als ein Element mit allen anderen Eigenschaftenelemente stehen darf, müssen alle vorausgehen `x:Arguments` auch als Elemente angegeben, und muss alle Inhalt "oder" Inner Text/Initialisierungstext vor.  
  
## <a name="see-also"></a>Siehe auch  
 [x:Arguments-Direktive](../../../docs/framework/xaml-services/x-arguments-directive.md)
