---
title: Gleichheitsoperatoren
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b1e5784de277d59c7bc945cbe7b605653eec7bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571016"
---
# <a name="equality-operators"></a>Gleichheitsoperatoren
In diesem Abschnitt wird erläutert, das Überladen von Gleichheitsoperatoren und bezieht sich auf `operator==` und `operator!=` als Gleichheitsoperatoren.  
  
 **X nicht** die Gleichheitsoperatoren und die andere Überladung.  
  
 **Führen Sie ✓** sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheitsoperatoren haben genau die gleiche Semantik und ähnliche Leistungsmerkmale.  
  
 Dies bedeutet, dass häufig `Object.Equals` außer Kraft gesetzt werden, wenn die Gleichheitsoperatoren überladen werden muss.  
  
 **X vermeiden** Auslösen von Ausnahmen von Gleichheitsoperatoren.  
  
 Gibt beispielsweise auf "false", wenn eines der Argumente null statt ist `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Gleichheitsoperatoren für Werttypen  
 **Führen Sie ✓** Überladen von Gleichheitsoperatoren für Werttypen, wenn Gleichheit sinnvoll ist.  
  
 In den meisten Programmiersprachen, es ist keine Standardimplementierung von `operator==` für Werttypen.  
  
## <a name="equality-operators-on-reference-types"></a>Gleichheitsoperatoren für Referenztypen  
 **X vermeiden** Überladen von Gleichheitsoperatoren auf änderbare Referenztypen.  
  
 Viele Sprachen haben integrierte Gleichheitsoperatoren für Verweistypen. Integrierte Operatoren in der Regel implementiert die Verweisgleichheit und viele Entwickler sind überrascht, wenn das Standardverhalten in der Wertgleichheit geändert wird.  
  
 Dieses Problem wird für unveränderliche Verweistypen verringert, da Unveränderlichkeit viel schwieriger, den Unterschied zwischen Verweisgleichheit und Wertgleichheit beachtet wird.  
  
 **X vermeiden** Überladen von Gleichheitsoperatoren für Verweistypen, bei die Implementierung wesentlich langsamer als der Verweisgleichheit wäre.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
