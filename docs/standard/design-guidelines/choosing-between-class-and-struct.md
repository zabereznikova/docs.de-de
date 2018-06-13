---
title: Auswählen zwischen Klasse und Struktur
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bb05b825113c025781a790dc206d500633a3b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573580"
---
# <a name="choosing-between-class-and-struct"></a>Auswählen zwischen Klasse und Struktur
Eine der grundlegenden Designentscheidungen, die jede Framework Designer portalclient ist, ob einen Typ als Klasse (ein Verweistyp) oder als eine Struktur (Werttyp) entworfen. Die Kenntnis der Unterschiede im Verhalten von Verweistypen und Werttypen ist in dieser Auswahl entscheidend.  
  
 Die erste der Unterschied zwischen der Referenztypen und Werttypen, die wir in Betracht ziehen, besteht darin, dass die Verweistypen sind, auf dem Heap reserviert und Garbage Collection, wohingegen Werttypen entweder auf dem Stapel zugeordnet werden oder Inline im mit Typen und freigegeben, wenn der Stapel Entlädt oder wenn ihrem enthaltenden Typ Ruft die Zuordnung aufgehoben. Daher werden speicherzuordnungen und Aufhebungen von Werttypen im Allgemeinen günstiger als speicherzuordnungen und Aufhebungen von Verweistypen sind.  
  
 Als Nächstes Arrays von Typen sind Verweisdaten Out-of-Line, d. h. das Array, das Elemente sind nur Verweise auf Instanzen des Verweistyps befinden, auf dem Heap zugeordnet. Wert Typ Arrays sind Inline, was bedeutet, dass die Elemente des Arrays die eigentlichen Instanzen des Werttyps sind zugeordnet. Aus diesem Grund werden speicherzuordnungen und Aufhebungen von Wert Typ Arrays weitaus günstigere als speicherzuordnungen und Aufhebungen von Verweis Typ Arrays. Darüber hinaus weisen Wert Typ Arrays in den meisten Fällen wesentlich bessere Positionierung von Verweisen auf.  
  
 Nächste Unterschied bezieht sich auf die speicherauslastung. Werttypen Abrufen mittels Boxing konvertiert, wenn ein Verweistyp oder eine der Schnittstellen, die sie implementieren umgewandelt. Erhalten sie mittels Unboxing konvertiert Wenn wieder auf den Werttyp umgewandelt. Da sind Objekte, die auf dem Heap zugeordnet sind und Garbage Collection, viel mit Boxing und unboxing können sich negativ auf dem Heap der Garbage Collector und letztlich die Leistung der Anwendung verfügen.  Im Gegensatz dazu erfolgt keine solche Boxing wie Verweistypen umgewandelt werden.  
  
 Im nächsten Schritt kopieren Verweis Zuweisung den Verweis, während der Zuweisung Wert den gesamten Wert kopieren. Daher sind Zuweisungen von großen Verweistypen günstiger als Zuweisungen von Datentypen mit umfangreichen Werten.  
  
 Schließlich werden die Verweistypen als Verweis übergeben, während Werttypen als Wert übergeben werden. Änderungen an den eine Instanz eines Verweistyps betreffen alle Verweise auf die Instanz verweist. Wert von Typinstanzen werden kopiert, wenn sie als Wert übergeben werden. Wenn eine Instanz eines Werttyps geändert wird, beeinflusst natürlich nicht seine Kopien. Da die Kopien werden nicht explizit vom Benutzer erstellt, aber es werden implizit erstellt, wenn Argumente übergeben oder zurückgeben Werte zurückgegeben werden, können Werttypen, die geändert werden können für viele Benutzer verwirrend sein. Aus diesem Grund sollten Werttypen unveränderlich sein.  
  
 Als Faustregel gilt sollte die meisten Typen in einem Framework Klassen sein. Es gibt jedoch einige Situationen, in denen die Merkmale eines Werttyps besser geeignet ist, verwenden von Strukturen zu vereinfachen.  
  
 **✓ GGF.** eine Struktur anstelle einer Klasse definieren, wenn Instanzen des Typs klein und im Allgemeinen kurzlebig sind oder in anderen Objekten eingebettet sind.  
  
 **X vermeiden** eine Struktur definieren, es sei denn, der Typ aller folgende Merkmale aufweist:  
  
-   Logisch stellt dar, einen einzelnen Wert, der ähnlich wie primitive Typen (`int`, `double`usw..).  
  
-   Es wurde eine Instanzgröße unter 16 Bytes.  
  
-   Er ist unveränderlich.  
  
-   Es wird kein häufig geschachtelt werden.  
  
 In allen anderen Fällen sollten Sie die Typen als Klassen definieren.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
