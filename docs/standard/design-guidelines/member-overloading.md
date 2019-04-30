---
title: Überladen von Membern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: b13f9e1551aec7e53ba1ac2ed0b9049d46b0a756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945544"
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
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
