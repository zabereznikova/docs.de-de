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
ms.openlocfilehash: 7590d5628f4951a8c7c2199f0e954007ed9fa962
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "50757425"
---
# <a name="choosing-between-class-and-struct"></a>Auswählen zwischen Klasse und Struktur
Eine der grundlegenden entwurfsentscheidungen, die alle Framework-Designer zeigt ist, ob einen Typ als eine Klasse (Referenztyp) oder als eine Struktur (Werttyp) entwerfen. Die Kenntnis der Unterschiede im Verhalten von Verweistypen und Werttypen ist in dieser Auswahl entscheidend.  
  
 Das erste der Unterschied zwischen Verweistypen und Werttypen, die wir berücksichtigen werden, besteht darin, dass Verweistypen sind, auf dem Heap reserviert und die Garbage Collection, während bei Werttypen werden entweder auf dem Stapel zugeordnet oder Inline im mit Typen und aufgehoben, wenn des Stapels Entlädt oder bei ihrem enthaltenden Typ Ruft die Zuordnung aufgehoben. Speicherzuordnungen und Aufhebungen von Werttypen werden daher im Allgemeinen günstiger sein als die speicherzuordnungen und Aufhebungen von Verweistypen sind.  
  
 Als Nächstes Arrays von Verweisen auf Typen werden Out-of-Line, d. h. das Array die Elemente sind nur die Verweise auf Instanzen des Referenztyps auf dem Heap zugeordnet. Wert Typ Arrays werden Inline, was bedeutet, dass die Elemente des Arrays, die eigentlichen Instanzen des Werttyps sind zugeordnet. Aus diesem Grund werden speicherzuordnungen und Aufhebungen von Typ Wertarrays wesentlich günstiger als speicherzuordnungen und Aufhebungen von Verweistyparrays. Darüber hinaus eine Wertarrays-Typ in der Mehrheit der Fälle viel bessere Positionierung von Verweisen auf.  
  
 Nächste Unterschied bezieht sich auf die speicherauslastung. Werttypen erste geschachtelt beim Konvertieren in ein Verweistyp oder eine der Schnittstellen, die sie implementieren. Sie erhalten nicht geschachtelte beim Konvertieren in den Werttyp zurück. Da Felder Objekte sind, die auf dem Heap reserviert sind und Garbage Collection zu viel Boxing und unboxing können sich negativ auf dem Heap der Garbage Collector und letztlich die Leistung der Anwendung haben.  Im Gegensatz dazu tritt auf, keine solche Boxing-Konvertierung, da Verweistypen umgewandelt werden. (Weitere Informationen finden Sie unter [Boxing und Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)).
  
 Kopieren Sie anschließend den Verweis-Typ-Zuweisungen die Referenz während der Wert bei typzuweisungen kopieren Sie den gesamten Wert. Aus diesem Grund sind Zuweisungen von großen Verweistypen günstiger als Zuweisungen von Typen mit umfangreichen Werten.  
  
 Schließlich werden die Verweistypen als Verweis übergeben, während Werttypen als Wert übergeben werden. Änderungen an einer Instanz eines Referenztyps Auswirkungen auf alle Verweise auf die Instanz verweist. Wert von Typinstanzen werden kopiert, wenn sie nach Wert übergeben werden. Wenn eine Instanz eines Werttyps geändert wird, wirkt es natürlich seine Kopien sich nicht. Da die Kopien werden nicht explizit vom Benutzer erstellt, aber es werden implizit erstellt werden, wenn Argumente übergeben oder zurückgegeben wird, dass die Werte zurückgegeben werden, können Werttypen, die geändert werden können, für viele Benutzer verwirrend sein. Aus diesem Grund sollten Werttypen unveränderlich sein.  
  
 Als Faustregel gilt sollten die meisten Typen in einem Framework Klassen sein. Es gibt jedoch einige Situationen, in denen die Merkmale eines Werttyps besser geeignet, verwenden Sie Strukturen zu erleichtern.  
  
 **✓ CONSIDER** eine Struktur anstelle einer Klasse definieren, wenn Instanzen des Typs klein und im Allgemeinen kurzlebig sind oder in anderen Objekten eingebettet sind.  
  
 **X AVOID** eine Struktur definieren, es sei denn, der Typ aller folgende Merkmale aufweist:  
  
-   Es logisch einen einzelnen Wert, der ähnlich wie primitive Typen darstellt (`int`, `double`usw..).  
  
-   Es hat eine Größe der Instanz unter 16 Bytes.  
  
-   Er ist unveränderlich.  
  
-   Es wird keine häufig geschachtelt werden.  
  
 In allen anderen Fällen sollten Sie die Typen als Klassen definieren.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
