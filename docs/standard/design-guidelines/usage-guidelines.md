---
title: Verwendungsrichtlinien
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: 57f6600f60e99c72b72c9f82856dc9eb631a9d4b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708996"
---
# <a name="usage-guidelines"></a>Verwendungsrichtlinien

Dieser Abschnitt enthält Richtlinien für die Verwendung gängiger Typen in öffentlich zugänglichen APIs. Es behandelt die direkte Verwendung integrierter Frameworktypen (z. b. Serialisierungsattribute) und das überladen allgemeiner Operatoren.
  
Die <xref:System.IDisposable?displayProperty=nameWithType>-Schnittstelle wird in diesem Abschnitt nicht behandelt, wird jedoch im Abschnitt Verwerfen von [Mustern](../garbage-collection/implementing-dispose.md) erläutert.

> [!NOTE]
> Richtlinien und zusätzliche Informationen über andere gängige, integrierte .NET Framework Typen finden Sie in den Referenz Themen zu den folgenden Themen: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>In diesem Abschnitt

[Arrays](arrays.md)  
[Attribute](attributes.md)  
[Sammlungen](guidelines-for-collections.md)  
[Serialisierung](serialization.md)  
[Verwendung von System.Xml](system-xml-usage.md)  
[Gleichheitsoperatoren](equality-operators.md)  

*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
