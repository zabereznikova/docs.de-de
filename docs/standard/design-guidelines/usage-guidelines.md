---
title: Verwendungsrichtlinien
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 761570b899a2a36391eb81dc7f42e13fff1f14ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778806"
---
# <a name="usage-guidelines"></a>Verwendungsrichtlinien

Dieser Abschnitt enthält Richtlinien für die Verwendung von häufig verwendeten Typen in öffentlich zugängliche-APIs. Er behandelt die direkte Verwendung von integrierten Framework-Typen (z. B. Serialisierungsattribute) und allgemeine Operatoren überladen.
  
Die <xref:System.IDisposable?displayProperty=nameWithType> Schnittstelle wird in diesem Abschnitt nicht behandelt, aber es wird erläutert, der [Dispose-Muster](../../../docs/standard/design-guidelines/dispose-pattern.md) Abschnitt.

> [!NOTE]
> Richtlinien und zusätzliche Informationen über andere gängige, integrierte .NET Framework-Typen finden Sie unter den Referenzthemen für die folgenden: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>In diesem Abschnitt

[Arrays](arrays.md)  
[Attribute](attributes.md)  
[Sammlungen](guidelines-for-collections.md)  
[Serialisierung](serialization.md)  
[Verwendung von System.Xml](system-xml-usage.md)  
[Gleichheitsoperatoren](equality-operators.md)  

*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
