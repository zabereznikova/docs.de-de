---
title: Geschachtelte Typen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: KrzysztofCwalina
ms.openlocfilehash: 22c14d05105154ff642cb8a44eda8e7c5d0575e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756870"
---
# <a name="nested-types"></a>Geschachtelte Typen
Ein geschachtelter Typ ist ein Typ, der innerhalb des Bereichs eines anderen Typs, der den einschließenden Typ aufgerufen wird, definiert. Ein geschachtelter Typ hat Zugriff auf alle Member des einschließenden Typs. Beispielsweise hat er Zugriff auf private Felder definiert, in den einschließenden Typ und geschützte Felder, die in alle vorausgehenden Elemente des einschließenden Typs definiert.  
  
 Im Allgemeinen sollten geschachtelte Typen sparsam verwendet werden. Hierfür gibt es mehrere Gründe: Einige Entwickler sind nicht vollständig mit dem Konzept vertraut. Diese Entwickler können z. B. Probleme mit der Syntax der Deklaration von Variablen von geschachtelten Typen haben. Geschachtelte Typen werden auch sehr eng mit ihrer einschließenden Typen verknüpft, und daher eignen sich nicht um die allgemeinen Typen sein.  
  
 Geschachtelte Typen eignen sich optimal für die Modellierung von Details zur Implementierung seiner einschließenden Typen. Benutzer müssen nur selten zum Deklarieren eines geschachtelten Typs und fast nie explizit Instanziieren von geschachtelten Typen verfügen. Der Enumerator eine Auflistung kann z. B. ein geschachtelter Typ von dieser Sammlung sein. Enumeratoren werden normalerweise vom einschließenden Typ instanziiert, und da viele Sprachen, die Foreach-Anweisung unterstützt, Enumerator Variablen nur selten vom Endbenutzer deklariert werden.  
  
 **✓ DO** geschachtelte Typen verwenden, wenn die Beziehung zwischen den geschachtelten Typ und der äußere Typ ist, sodass Memberzugriff Semantik wünschenswert ist.  
  
 **X DO NOT** verwenden öffentlichen geschachtelten Typen als eine logische Gruppierung zu erstellen; für diese Namespaces verwenden.  
  
 **X AVOID** öffentlich verfügbar gemacht werden geschachtelte Typen. Die einzige Ausnahme hierbei ist, wenn es sich bei Variablen des geschachtelten Typs deklariert werden, nur in seltenen Szenarien wie z. B. Szenarios für das Erstellen von Unterklassen oder andere erweiterte anpassen müssen.  
  
 **X DO NOT** geschachtelte Typen verwenden, wenn der Typ wahrscheinlich außerhalb der enthaltende Typ verwiesen werden.  
  
 Beispielsweise sollte eine Enumeration, die an eine Methode für eine Klasse definiert, nicht als geschachtelter Typ in der Klasse definiert werden.  
  
 **X DO NOT** geschachtelte Typen verwenden, wenn sie vom Clientcode instanziiert werden müssen.  Wenn ein Typ einen öffentlichen Konstruktor verfügt, sollten sie wahrscheinlich nicht geschachtelt werden.  
  
 Wenn ein Typ instanziiert werden kann, ist das an, dass der Typ ist ein Ausgangspunkt für das Framework selbst erscheint (Sie können erstellen, damit arbeiten und zerstören sie ohne jemals mit dem äußeren Typ), und sollte daher nicht geschachtelt werden. Interne Typen sollten nicht häufig wiederverwendet werden außerhalb des äußeren Typs ohne Beziehung überhaupt zu der äußere Typ.  
  
 **X DO NOT** einen geschachtelten Typ als Member einer Schnittstelle definieren. Ein Konstrukt dieser Art werden von vielen Sprachen nicht unterstützt.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
