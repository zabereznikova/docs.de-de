---
title: "Inherits Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Inherits"
  - "Inherits"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Inherits statement"
  - "Inherits statement, syntax"
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Inherits Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Bewirkt, dass die aktuelle Klasse oder Schnittstelle Attribute, Variablen, Eigenschaften, Prozeduren und Ereignisse von einer anderen Klasse oder Gruppe von Schnittstellen erbt.  
  
## Syntax  
  
```  
Inherits basetypenames  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`basetypenames`|Erforderlich.  Der Name der Klasse, von der diese Klasse abgeleitet wird.<br /><br /> \- oder \-<br /><br /> Die Namen der Schnittstellen, von denen diese Schnittstelle abgeleitet wird.  Trennen Sie mehrere Namen mit Komma.|  
  
## Hinweise  
 Die `Inherits`\-Anweisung muss die erste nicht leere, kommentarlose Zeile in einer Klassen\- oder Schnittstellendefinition sein.  Sie muss direkt auf die `Class`\-Anweisung oder die `Interface`\-Anweisung folgen.  
  
 Sie können `Inherits` nur in einer Klasse oder einer Schnittstelle verwenden.  Daher kann der Deklarationskontext für Vererbung keine Quelldatei, kein Namespace, keine Struktur, kein Modul, keine Prozedur und kein Block sein.  
  
## Regeln  
  
-   **Klassenvererbung.** Wenn eine Klasse die `Inherits`\-Anweisung verwendet, können Sie nur eine Basisklasse angeben.  
  
     Eine Klasse kann nicht von einer Klasse erben, die in ihr geschachtelt ist.  
  
-   **Schnittstellenvererbung.** Wenn eine Schnittstelle die `Inherits`\-Anweisung verwendet, können Sie eine oder mehrere Basisschnittstellen angeben.  Sie können zwei Schnittstellen vererben, auch wenn jede Schnittstelle einen Member mit dem gleichen Namen definiert.  In diesem Fall muss der implementierende Code Namensqualifizierung verwenden, um anzugeben, welcher Member implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer restriktiveren Zugriffsebene erben.  Eine Schnittstelle mit `Public`\-Zugriff kann beispielweise nicht von einer Schnittstelle mit `Friend`\-Zugriff erben.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle erben, die in ihr geschachtelt ist.  
  
 Ein Beispiel für Klassenvererbung in .NET Framework ist die <xref:System.ArgumentException>\-Klasse, die von der <xref:System.SystemException>\-Klasse erbt.  Hierdurch erhält <xref:System.ArgumentException> alle vordefinierten Eigenschaften und Prozeduren, die für Systemausnahmen erforderlich sind, z. B. die <xref:System.Exception.Message%2A>\-Eigenschaft und die <xref:System.Exception.ToString%2A>\-Methode.  
  
 Ein Beispiel für Schnittstellenvererbung in .NET Framework ist die <xref:System.Collections.ICollection>\-Schnittstelle, die von der <xref:System.Collections.IEnumerable>\-Schnittstelle erbt.  Dies bewirkt, dass <xref:System.Collections.ICollection> die Definition des Enumerators erbt, der zum Durchlaufen einer Auflistung erforderlich ist.  
  
## Beispiel  
 In diesem Beispiel wird die `Inherits`\-Anweisung verwendet, um zu zeigen, wie die Klasse `thisClass` alle Member der Basisklasse `anotherClass` erben kann.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Vererbung von mehreren Schnittstellen veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 Die Schnittstelle `thisInterface` enthält jetzt alle Definitionen in den Schnittstellen <xref:System.IComparable>, <xref:System.IDisposable> und <xref:System.IFormattable>. Die geerbten Member ermöglichen den typspezifischen Vergleich von zwei Objekten, die Freigabe reservierter Ressourcen bzw. die Darstellung des Werts eines Objekts als `String`.  Eine Klasse, die `thisInterface` implementiert, muss jeden Member jeder Basisschnittstelle implementieren.  
  
## Siehe auch  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)