---
title: Attribute
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: KrzysztofCwalina
ms.openlocfilehash: 6d4cc6615b7f7346e9c8fc2a7264025f318c8a3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698881"
---
# <a name="attributes"></a>Attribute
<xref:System.Attribute?displayProperty=nameWithType> eine Basisklasse wird zum Definieren von benutzerdefinierter Attributen verwendet werden.  
  
 Attribute sind Anmerkungen, die die Programmierelemente, z. B. Assemblys, Typen, Member und Parameter hinzugefügt werden können. Sie werden in den Metadaten der Assembly gespeichert und zur Laufzeit mithilfe der Reflektions-APIs zugegriffen werden können. Das Framework definiert z. B. die <xref:System.ObsoleteAttribute>, die angewendet werden können, auf einen Typ oder ein Element aus, um anzugeben, dass der Typ oder Member veraltet ist.  
  
 Attribute können eine oder mehrere Eigenschaften verfügen, die zusätzliche Daten, die im Zusammenhang mit der das Attribut enthalten. Z. B. `ObsoleteAttribute` könnte natürlich zusätzliche Informationen zu dieser Version in die ein Typ oder Member als veraltet markiert wurde und die Beschreibung der neuen APIs ersetzt die veraltete API.  
  
 Einige Eigenschaften eines Attributs müssen angegeben werden, wenn das Attribut angewendet wird. Diese sind als die erforderlichen Eigenschaften oder die erforderlichen Argumente bezeichnet, da sie als Konstruktorparameter mit Feldern fester Breite dargestellt werden. Z. B. die <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> Eigenschaft der <xref:System.Diagnostics.ConditionalAttribute> ist eine erforderliche Eigenschaft.  
  
 Eigenschaften, die nicht unbedingt angegeben werden, wenn das Attribut angewendet wird, werden optionale Eigenschaften (oder optionalen Argumenten) bezeichnet. Sie werden durch festlegbaren Eigenschaften dargestellt. Compiler bieten speziellen Syntax zum Festlegen dieser Eigenschaften, wenn ein Attribut angewendet wird. Z. B. die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> Eigenschaft darstellt, ein optionales Argument.  
  
 **✓ DO** benennen Sie benutzerdefinierte Attributklassen mit dem Suffix "-Attribut" an.  
  
 **✓ DO** gelten die <xref:System.AttributeUsageAttribute> zu benutzerdefinierten Attributen.  
  
 **✓ DO** festlegbare Eigenschaften bereitstellen, für die optionalen Argumente.  
  
 **✓ DO** nur Get-Eigenschaften für die erforderlichen Argumente bereitstellen.  
  
 **✓ DO** Konstruktorparameter zum Initialisieren der Eigenschaften, die erforderlichen Argumente bereitstellen. Jeder Parameter muss den gleichen Namen (auch mit unterschiedlicher Groß-/Kleinschreibung) als die entsprechende Eigenschaft verfügen.  
  
 **X AVOID** Konstruktorparameter zum Initialisieren der Eigenschaften, die die optionalen Argumente bereitstellen.  
  
 Das heißt, keine Eigenschaften, die mit einem Setter und einen Konstruktor festgelegt werden können. Diese Richtlinie ist sehr deutlich, welche Argumente optional sind und die erforderlich sind, und vermeidet zwei Möglichkeiten zum erledigen des gleiche.  
  
 **X AVOID** Überladen von Konstruktoren des benutzerdefinierten Attributs.  
  
 Müssen nur über einen Konstruktor kommuniziert eindeutig für den Benutzer der Argumente erforderlich sind und welche optional sind.  
  
 **✓ DO** versiegeln Sie benutzerdefinierte Attributklassen, falls möglich. Dies beschleunigt die Suche für das Attribut.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
