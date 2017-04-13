---
title: "x:FactoryMethod Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XAML. x:FactoryMethod directive [XAML Services]"
  - "FactoryMethod directive in XAML [XAML Services]"
  - "x:FactoryMethod directive [XAML Services]"
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# x:FactoryMethod Directive
Gibt eine andere Methode als ein Konstruktor an, den ein XAML\-Prozessor zum Initialisieren eines Objekts verwenden sollte, nachdem sein Unterstützungstyp aufgelöst wurde.  
  
## XAML\-Attributverwendung, keine x:Argumente  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## XAML\-Attributverwendung, x:Arguments als Element\(e\)  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`methodname`|Der Zeichenfolgenmethodenname einer Methode, die XAML\-Prozessoren aufrufen, um die als `object` angegebene Instanz zu initialisieren.  Siehe Hinweise.|  
|`oneOrMoreObjectElements`|Ein oder mehrere Objektelemente für Objekte, die Factorymethodenparameter angeben.  Die Reihenfolge ist bedeutend. Sie gibt die Reihenfolge an, in der Argumente an die Factorymethode weitergegeben werden sollen.|  
  
## Hinweise  
 Wenn `methodname` eine Instanzmethode ist, kann sie nicht qualifiziert werden.  
  
 Statische Methoden als Factory\-Methoden werden unterstützt.  Wenn `methodname` eine statische Methode ist, wird `methodname` als eine *typeName*\-*methodName*\-Kombination bereitgestellt, wobei *Typname* die Klasse benennt, die die statische Factorymethode definiert.  *Typname* kann durch ein Präfix qualifiziert sein, wenn er auf einen Typ in einem zugeordneten XMLNS\-Objekt verweist.  *Typname* kann ein anderer Typ sein als `typeof(``object``)`.  
  
 Die Factorymethode muss eine deklarierte öffentliche Methode des Typs sein, der das relevante Objektelement unterstützt.  
  
 Die Factorymethode muss eine Instanz zurückgeben, die dem relevanten Objekt zuweisbar ist.  Factorymethoden sollten nie Null zurückgeben.  
  
 `x:Arguments` basiert auf einem Prinzip der besten Übereinstimmung für Signaturen von Factorymethoden.  Das Zusammenpassen wertet zuerst die Parameteranzahl aus.  Wenn es mehr als eine mögliche Übereinstimmung für eine Parameteranzahl gibt, wird der Parametertyp ausgewertet, und die beste Übereinstimmung ermittelt.  Wenn es immer noch Mehrdeutigkeiten nach dieser Phase der Auswertung gibt, ist das XAML\-Prozessorverhalten nicht definiert.  
  
 Die Verwendung des `x:FactoryMethod`\-Elements ist keine Eigenschaftenelementverwendung im typischen Sinn, da das Direktivenmarkup nicht auf den Objekttyp des enthaltenen Elements verweist.  Es wird erwartet, dass Elementverwendung weniger gängig als Attributverwendung ist.  `x:Arguments` \(entweder Attribut\- oder Elementverwendung\) kann mit der `x:FactoryMethod`\-Elementverwendung verwendet werden, was in den Abschnitten Verwendung jedoch nicht ausdrücklich hervorgeht.  
  
 `x:FactoryMethod` als Element muss vor jedem anderen Eigenschaftenelement, jedem `x:Arguments`, das auch in Elementform angegeben ist, und jedem Inhalt\/inneren Text oder Initialisierungstext stehen.  
  
## Siehe auch  
 [x:Arguments Directive](../../../docs/framework/xaml-services/x-arguments-directive.md)