---
title: Schnittstellenentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c687d7622e82ee206b2201760818827398f8543b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863721"
---
# <a name="interface-design"></a>Schnittstellenentwurf
Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, gibt es Fälle, in denen Schnittstellen sind besser geeignet, oder sind die einzige Option.  
  
 Die CLR unterstützt keine mehrfache Vererbung (z. B. CLR-Klassen aus mehr als einer Basisklasse erben können nicht), aber es lässt sich auf Typen, um eine oder mehrere Schnittstellen zusätzlich zum erben von einer Basisklasse zu implementieren. Schnittstellen werden daher häufig verwendet, um die Auswirkungen der mehrfachvererbung zu erzielen. Z. B. <xref:System.IDisposable> ist eine Schnittstelle, über die Typen, die unabhängig von der alle anderen Vererbungshierarchie Disposability zu unterstützen, in dem sie teilnehmen möchten.  
  
 Die andere Situation, in der, die Definition eine Schnittstelle geeignet ist, ist in eine gemeinsame Schnittstelle, die von mehreren Typen wählen, darunter einige Werttypen unterstützt werden können. Werttypen können nicht von Typen erben, außer <xref:System.ValueType>, aber sie können Schnittstellen implementieren, also über eine Schnittstelle ist die einzige Option, um einen gemeinsamen Basistyp bereitzustellen.  
  
 **✓ DO** definieren Sie eine Schnittstelle aus, wenn Sie einige gemeinsame-API benötigen, von einem Satz von Typen unterstützt werden müssen, die Werttypen enthält.  
  
 **✓ CONSIDER** zum Definieren einer Schnittstelle, wenn Sie seine Funktionalität auf Typen zu unterstützen, die bereits von einem anderen Typ erben müssen.  
  
 **X AVOID** Markerschnittstellen (ohne Member) verwenden.  
  
 Wenn Sie eine Klasse mit der ein bestimmtes Merkmal (Marker) markieren möchten, verwenden Sie im Allgemeinen eine Schnittstelle, anstatt ein benutzerdefiniertes Attribut.  
  
 **✓ DO** Geben Sie mindestens einen Typ, die Implementierung einer Schnittstelle.  
  
 Dies erleichtert das Design der Schnittstelle zu überprüfen. Z. B. <xref:System.Collections.Generic.List%601> ist eine Implementierung der <xref:System.Collections.Generic.IList%601> Schnittstelle.  
  
 **✓ DO** Geben Sie mindestens eine API, die jede Schnittstelle nutzt Sie definieren (eine Methode, die die Schnittstelle als Parameter oder einer Eigenschaft annimmt, die als Schnittstelle eingegeben wird).  
  
 Dies erleichtert den Entwurf der Benutzeroberfläche zu überprüfen. Z. B. <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> nutzt die <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> Schnittstelle.  
  
 **X DO NOT** Hinzufügen von Mitgliedern zu einer Schnittstelle, die zuvor gesendet wurde.  
  
 Auf diese Weise wird die Implementierungen der Schnittstelle unterbrochen. Sie sollten eine neue Schnittstelle erstellen, um Versionsprobleme zu vermeiden.  
  
 Außer den Situationen, in diesen Richtlinien beschrieben sollten Sie statt Klassen Schnittstellen im Allgemeinen wählen Sie in Design wiederverwendbarer Bibliotheken von verwaltetem Code.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
