---
title: Geschachtelte Typen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 681e11ef3994e4c38dee9f99c6c82cc4b103a0db
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="nested-types"></a>Geschachtelte Typen
Ein geschachtelter Typ ist ein Typ, der innerhalb des Gültigkeitsbereichs eines anderen Typs, der aufgerufen wird, den einschließenden Typ definiert. Ein geschachtelter Typ hat Zugriff auf alle Member des einschließenden Typs. Beispielsweise verfügt es über Zugriff auf private Felder, die in der einschließende Typ und zu schützende in alle vorausgehenden Elemente des einschließenden Typs definierten öffentlichen Felder definiert.  
  
 Im Allgemeinen sollte nur selten geschachtelte Typen verwendet werden. Hierfür gibt es mehrere Gründe: Einige Entwickler sind nicht mit dem Konzept vollständig vertraut. Diese Entwickler könnte z. B. Probleme mit der Syntax des Deklarieren von Variablen von geschachtelten Typen haben. Geschachtelte Typen sind ebenfalls sehr eng mit ihren einschließenden Typen verbunden und daher eignen sich nicht um die allgemeinen Typen sein.  
  
 Geschachtelte Typen eignen sich am besten für die Modellierung von Implementierungsdetails der einschließenden Typen. Der Endbenutzer müssen nur selten in Variablen eines geschachtelten Typs deklarieren und fast nie müssen in der geschachtelte Typen explizit instanziieren. Der Enumerator eine Auflistung kann z. B. ein geschachtelter Typ dieser Sammlung sein. Enumeratoren werden normalerweise vom einschließenden Typ instanziiert, und da viele Sprachen zu die foreach-Anweisung unterstützen Enumerator Variablen selten vom Endbenutzer deklariert werden.  
  
 **Führen Sie ✓** geschachtelte Typen verwenden, wenn die Beziehung zwischen den geschachtelten Typ und der äußere Typ ist, sodass Memberzugriff Semantik wünschenswert ist.  
  
 **X nicht** verwenden öffentlichen geschachtelten Typen als eine logische Gruppierung zu erstellen; für diese Namespaces verwenden.  
  
 **X vermeiden** öffentlich verfügbar gemacht werden geschachtelte Typen. Die einzige Ausnahme hierbei ist, wenn Variablen des geschachtelten Typs müssen nur in seltenen Szenarien wie z. B. Erstellen von Unterklassen oder andere erweiterte Anpassungsszenarien deklariert werden.  
  
 **X nicht** geschachtelte Typen verwenden, wenn der Typ wahrscheinlich außerhalb der enthaltende Typ verwiesen werden.  
  
 Eine Enumeration, die an eine Methode, die für eine Klasse definierten übergeben darf beispielsweise nicht als ein geschachtelter Typ in der Klasse definiert werden.  
  
 **X nicht** geschachtelte Typen verwenden, wenn sie vom Clientcode instanziiert werden müssen.  Wenn ein Typ einen öffentlichen Konstruktor verfügt, sollte es wahrscheinlich nicht geschachtelt werden.  
  
 Wenn ein Typ nicht instanziiert werden kann, das erscheint, um anzugeben, der Typ ist für das Framework selbst geeignet (Sie können erstellen, arbeiten und ohne jemals mithilfe des äußeren Typs zu zerstören), und sollte daher nicht geschachtelt werden. Interne Typen sollten nicht weit wiederverwendet werden außerhalb des äußeren Typs ohne eine Beziehung ist in der äußeren Typ.  
  
 **X nicht** einen geschachtelten Typ als Member einer Schnittstelle definieren. Dieses Konstrukt wird von zahlreichen Sprachen nicht unterstützt.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
