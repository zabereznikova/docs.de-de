---
title: Schnittstellenentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 06b2e0d281314f3bd6346a7dbbd8bb56928fe58b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709295"
---
# <a name="interface-design"></a>Schnittstellenentwurf
Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, gibt es Fälle, in denen Schnittstellen besser geeignet sind oder die einzige Option sind.  
  
 Die CLR unterstützt keine mehrfache Vererbung (d. h. CLR-Klassen können nicht von mehreren Basisklassen erben), aber es ist möglich, dass Typen zusätzlich zum Erben von einer Basisklasse eine oder mehrere Schnittstellen implementieren. Daher werden Schnittstellen häufig verwendet, um die Auswirkung der Mehrfachvererbung zu erzielen. <xref:System.IDisposable> ist beispielsweise eine Schnittstelle, die es Typen ermöglicht, disposability unabhängig von jeder anderen Vererbungs Hierarchie zu unterstützen, in der Sie teilnehmen möchten.  
  
 Eine andere Situation, in der eine Schnittstelle definiert wird, ist das Erstellen einer gemeinsamen Schnittstelle, die von verschiedenen Typen unterstützt werden kann, einschließlich einiger Werttypen. Werttypen können nicht von anderen Typen als <xref:System.ValueType>erben, Sie können jedoch Schnittstellen implementieren, sodass die Verwendung einer Schnittstelle die einzige Option ist, um einen gemeinsamen Basistyp bereitzustellen.  
  
 **✓ DO** definieren Sie eine Schnittstelle aus, wenn Sie einige gemeinsame-API benötigen, von einem Satz von Typen unterstützt werden müssen, die Werttypen enthält.  
  
 **✓ CONSIDER** zum Definieren einer Schnittstelle, wenn Sie seine Funktionalität auf Typen zu unterstützen, die bereits von einem anderen Typ erben müssen.  
  
 **X AVOID** Markerschnittstellen (ohne Member) verwenden.  
  
 Wenn Sie eine Klasse als ein bestimmtes Merkmal (Marker) markieren müssen, verwenden Sie im Allgemeinen ein benutzerdefiniertes Attribut anstelle einer Schnittstelle.  
  
 **✓ DO** Geben Sie mindestens einen Typ, die Implementierung einer Schnittstelle.  
  
 Auf diese Weise können Sie den Entwurf der-Schnittstelle überprüfen. Beispielsweise ist <xref:System.Collections.Generic.List%601> eine Implementierung der <xref:System.Collections.Generic.IList%601>-Schnittstelle.  
  
 **✓ DO** Geben Sie mindestens eine API, die jede Schnittstelle nutzt Sie definieren (eine Methode, die die Schnittstelle als Parameter oder einer Eigenschaft annimmt, die als Schnittstelle eingegeben wird).  
  
 Auf diese Weise kann der Schnittstellen Entwurf überprüft werden. Beispielsweise <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> die <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>-Schnittstelle verwendet.  
  
 **X DO NOT** Hinzufügen von Mitgliedern zu einer Schnittstelle, die zuvor gesendet wurde.  
  
 Dies würde die Implementierungen der-Schnittstelle unterbrechen. Sie sollten eine neue Schnittstelle erstellen, um Versions Probleme zu vermeiden.  
  
 Mit Ausnahme der in diesen Richtlinien beschriebenen Situationen sollten Sie im allgemeinen Klassen anstelle von Schnittstellen für das Entwerfen von wiederverwendbaren Bibliotheken für verwalteten Code auswählen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
