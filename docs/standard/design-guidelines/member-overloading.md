---
title: Überladen von Membern
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2127497d294cbfd4e1bb24d033f432378627ff13
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353173"
---
# <a name="member-overloading"></a>Überladen von Membern
Überladen von Membern bedeutet das Erstellen von zwei oder mehr Elemente auf dem gleichen Typ, die unterscheiden sich nur hinsichtlich der Anzahl oder den Typ der Parameter, aber den gleichen Namen haben. Z. B. im folgenden die `WriteLine` -Methode ist überladen:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Da nur Methoden, Konstruktoren und indizierte Eigenschaften Parameter verfügen können, können nur für die Elemente überladen werden.  
  
 Überladen ist eine der wichtigsten Techniken zur Verbesserung der benutzerfreundlichkeit, Produktivität und Lesbarkeit von wiederverwendbaren Bibliotheken. Auf der Anzahl von Parametern überladen ermöglicht es, einfachere Versionen von Konstruktoren und Methoden enthalten. Für den Parametertyp überladen ermöglicht die mit dem gleichen Elementnamen für Elemente, die identische Vorgänge für eine ausgewählte Gruppe verschiedener Typen.  
  
 **✓ DO** versuchen, beschreibende Parameternamen zu verwenden, um anzugeben, die Standardeinstellung von kürzeren Überladungen verwendet.  
  
 **X AVOID** nach dem Zufallsprinzip varying Parameternamen in Überladungen. Wenn ein Parameter in einer Überladung dieselbe Eingabe als Parameter in eine andere Überladung darstellt, sollte der Parameter den gleichen Namen aufweisen.  
  
 **X AVOID** Mitglieder überlastet werden in der Reihenfolge der Parameter in inkonsistent. Parameter mit dem gleichen Namen in der gleichen Position in der alle Überladungen angezeigt.  
  
 **✓ DO** stellen nur die längste Überladung virtuellen (wenn Erweiterbarkeit erforderlich ist). Kürzere Überladungen sollten einfach bis zu einer längeren Überladung aufrufen.  
  
 **X DO NOT** verwenden `ref` oder `out` Modifizierer zum Überladen von Membern.  
  
 Aufrufe der Überladungen wie folgt können nicht bei einigen Sprachen aufgelöst werden. Darüber hinaus sollte solche Überladungen in der Regel völlig unterschiedliche Semantiken und wahrscheinlich nicht Überladungen jedoch zwei separate Methoden stattdessen.  
  
 **X DO NOT** Überladungen mit Parametern, die an der gleichen Position und ähnliche Typen noch mit einer anderen Semantik haben.  
  
 **✓ DO** zulassen `null` für optionale Argumente übergeben werden soll.  
  
 **✓ DO** verwenden Member überladen, anstatt Elemente mit Standardargumenten definieren.  
  
 Standardargumente sind nicht CLS-kompatibel.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
