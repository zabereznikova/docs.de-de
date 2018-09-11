---
title: Attributes1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51aa91b1acbae9f1a15ac12441090dd4c1c2dcb1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259491"
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
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
