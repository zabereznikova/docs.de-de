---
title: Attribute
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: ff38cfdc228fd1eae1ace734ed2688c62c66499a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709555"
---
# <a name="attributes"></a>Attribute
<xref:System.Attribute?displayProperty=nameWithType> ist eine Basisklasse, die zum Definieren von benutzerdefinierten Attributen verwendet wird.  
  
 Attribute sind Anmerkungen, die Programmier Elementen wie Assemblys, Typen, Membern und Parametern hinzugefügt werden können. Sie werden in den Metadaten der Assembly gespeichert und können zur Laufzeit mithilfe der reflektionsapis aufgerufen werden. Das Framework definiert z. b. die <xref:System.ObsoleteAttribute>, die auf einen Typ oder einen Member angewendet werden kann, um anzugeben, dass der Typ oder Member veraltet ist.  
  
 Attribute können über eine oder mehrere Eigenschaften verfügen, die zusätzliche Daten enthalten, die sich auf das Attribut beziehen. Beispielsweise können `ObsoleteAttribute` zusätzliche Informationen über das Release enthalten, in dem ein Typ oder ein Mitglied als veraltet eingestuft wurde, und die Beschreibung der neuen APIs, die die veraltete API ersetzen.  
  
 Einige Eigenschaften eines Attributs müssen angegeben werden, wenn das Attribut angewendet wird. Diese werden als erforderliche Eigenschaften oder erforderliche Argumente bezeichnet, da Sie als positionelle Konstruktorparameter dargestellt werden. Die <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>-Eigenschaft der <xref:System.Diagnostics.ConditionalAttribute> ist beispielsweise eine erforderliche Eigenschaft.  
  
 Eigenschaften, die nicht unbedingt angegeben werden müssen, wenn das-Attribut angewendet wird, werden optionale Eigenschaften (oder optionale Argumente) genannt. Sie werden durch festleg bare Eigenschaften dargestellt. Compiler stellen spezielle Syntax bereit, um diese Eigenschaften festzulegen, wenn ein Attribut angewendet wird. Die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>-Eigenschaft stellt z. b. ein optionales Argument dar.  
  
 **✓ DO** benennen Sie benutzerdefinierte Attributklassen mit dem Suffix "-Attribut" an.  
  
 **✓ DO** gelten die <xref:System.AttributeUsageAttribute> zu benutzerdefinierten Attributen.  
  
 **✓ DO** festlegbare Eigenschaften bereitstellen, für die optionalen Argumente.  
  
 **✓ DO** nur Get-Eigenschaften für die erforderlichen Argumente bereitstellen.  
  
 **✓ DO** Konstruktorparameter zum Initialisieren der Eigenschaften, die erforderlichen Argumente bereitstellen. Jeder Parameter sollte denselben Namen haben (obwohl er mit unterschiedlicher Groß-/Kleinschreibung identisch ist) wie die entsprechende Eigenschaft.  
  
 **X AVOID** Konstruktorparameter zum Initialisieren der Eigenschaften, die die optionalen Argumente bereitstellen.  
  
 Mit anderen Worten, Sie verfügen nicht über Eigenschaften, die sowohl mit einem Konstruktor als auch mit einem Setter festgelegt werden können. Diese Richtlinie gibt explizit an, welche Argumente optional und welche erforderlich sind, und vermeidet zwei Möglichkeiten, das gleiche zu tun.  
  
 **X AVOID** Überladen von Konstruktoren des benutzerdefinierten Attributs.  
  
 Nur ein Konstruktor kommuniziert eindeutig mit dem Benutzer, welche Argumente erforderlich und welche optional sind.  
  
 **✓ DO** versiegeln Sie benutzerdefinierte Attributklassen, falls möglich. Dadurch wird das Suchen nach dem Attribut beschleunigt.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
