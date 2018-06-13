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
ms.openlocfilehash: 2c77f08cd573dc40083718b783ae01233ca00766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573554"
---
# <a name="member-overloading"></a>Überladen von Membern
Überladen von Membern bedeutet das Erstellen von zwei oder mehr Elemente für den gleichen Typ, die denselben Namen aufweisen, unterscheiden sich nur hinsichtlich der Anzahl oder dem Typ der Parameter. Im folgenden wird beispielsweise der `WriteLine` -Methode ist überladen:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Da nur Methoden, Konstruktoren und indizierte Eigenschaften über Parameter verfügen können, können nur für die Elemente überladen werden.  
  
 Überladen ist eine der wichtigsten Methoden zur Verbesserung der Nutzbarkeit und Produktivität und Lesbarkeit wieder verwendbare Bibliotheken. Auf der Anzahl von Parametern überladen ermöglicht die einfachere Versionen von Konstruktoren und Methoden bereitstellen. Überladen für den Parametertyp erleichtert möglich, demselben Membernamen für Elemente, die identische Vorgänge für eine ausgewählte Gruppe von verschiedenen Typen zu verwenden.  
  
 **Führen Sie ✓** versuchen, beschreibende Parameternamen zu verwenden, um anzugeben, die Standardeinstellung von kürzeren Überladungen verwendet.  
  
 **X vermeiden** nach dem Zufallsprinzip varying Parameternamen in Überladungen. Wenn ein Parameter in einer Überladung dieselbe Eingabe als Parameter in einer anderen Überladung darstellt, sollte der Parameter denselben Namen aufweisen.  
  
 **X vermeiden** Mitglieder überlastet werden in der Reihenfolge der Parameter in inkonsistent. Parameter mit dem gleichen Namen sollte in der gleichen Position alle Überladungen angezeigt werden.  
  
 **Führen Sie ✓** stellen nur die längste Überladung virtuellen (wenn Erweiterbarkeit erforderlich ist). Kürzere Überladungen sollten einfach über eine längere Überladung aufrufen.  
  
 **X nicht** verwenden `ref` oder `out` Modifizierer zum Überladen von Membern.  
  
 Für einige Sprachen nicht aufrufen an Überladungen wie folgt aufgelöst werden. Darüber hinaus sollte solche Überladungen wurden in der Regel vollständig unterschiedliche Semantiken wahrscheinlich auch nicht Überladungen jedoch zwei separate Methoden stattdessen.  
  
 **X nicht** Überladungen mit Parametern, die an der gleichen Position und ähnliche Typen noch mit einer anderen Semantik haben.  
  
 **Führen Sie ✓** zulassen `null` für optionale Argumente übergeben werden soll.  
  
 **Führen Sie ✓** verwenden Member überladen, anstatt Elemente mit Standardargumenten definieren.  
  
 Standardargumente sind nicht CLS-kompatibel.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
