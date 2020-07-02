---
title: Attribute
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: 3c0e1b8c20042c085d4ace996a084cbd464d3b21
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617560"
---
# <a name="attributes"></a>Attribute
<xref:System.Attribute?displayProperty=nameWithType>ist eine Basisklasse, die zum Definieren von benutzerdefinierten Attributen verwendet wird.

 Attribute sind Anmerkungen, die Programmier Elementen wie Assemblys, Typen, Membern und Parametern hinzugefügt werden können. Sie werden in den Metadaten der Assembly gespeichert und können zur Laufzeit mithilfe der reflektionsapis aufgerufen werden. Das Framework definiert z. b. das-Element <xref:System.ObsoleteAttribute> , das auf einen Typ oder einen Member angewendet werden kann, um anzugeben, dass der Typ oder Member veraltet ist.

 Attribute können über eine oder mehrere Eigenschaften verfügen, die zusätzliche Daten enthalten, die sich auf das Attribut beziehen. Beispielsweise `ObsoleteAttribute` könnte zusätzliche Informationen über das Release enthalten, in dem ein Typ oder ein Mitglied als veraltet eingestuft wurde, und die Beschreibung der neuen APIs, die die veraltete API ersetzen.

 Einige Eigenschaften eines Attributs müssen angegeben werden, wenn das Attribut angewendet wird. Diese werden als erforderliche Eigenschaften oder erforderliche Argumente bezeichnet, da Sie als positionelle Konstruktorparameter dargestellt werden. Beispielsweise ist die- <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> Eigenschaft des <xref:System.Diagnostics.ConditionalAttribute> eine erforderliche Eigenschaft.

 Eigenschaften, die nicht unbedingt angegeben werden müssen, wenn das-Attribut angewendet wird, werden optionale Eigenschaften (oder optionale Argumente) genannt. Sie werden durch festleg bare Eigenschaften dargestellt. Compiler stellen spezielle Syntax bereit, um diese Eigenschaften festzulegen, wenn ein Attribut angewendet wird. Beispielsweise stellt die- <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> Eigenschaft ein optionales Argument dar.

 ✔️ Benennen Sie benutzerdefinierte Attribut Klassen mit dem Suffix "Attribute".

 ✔️ Das <xref:System.AttributeUsageAttribute> auf benutzerdefinierte Attribute anwenden.

 ✔️ Stellen festleg bare Eigenschaften für optionale Argumente bereit.

 ✔️ Stellen nur die Get-only-Eigenschaften für erforderliche Argumente bereit.

 ✔️ die Konstruktorparameter bereitstellen, um die Eigenschaften zu initialisieren, die den erforderlichen Argumenten entsprechen. Jeder Parameter sollte denselben Namen haben (obwohl er mit unterschiedlicher Groß-/Kleinschreibung identisch ist) wie die entsprechende Eigenschaft.

 ❌Vermeiden Sie die Angabe von Konstruktorparametern, um die Eigenschaften zu initialisieren, die den optionalen Argumenten entsprechen.

 Mit anderen Worten, Sie verfügen nicht über Eigenschaften, die sowohl mit einem Konstruktor als auch mit einem Setter festgelegt werden können. Diese Richtlinie gibt explizit an, welche Argumente optional und welche erforderlich sind, und vermeidet zwei Möglichkeiten, das gleiche zu tun.

 ❌Vermeiden Sie das überladen benutzerdefinierter Attributkonstruktoren.

 Nur ein Konstruktor kommuniziert eindeutig mit dem Benutzer, welche Argumente erforderlich und welche optional sind.

 Verwenden Sie nach Möglichkeit ✔️ benutzerdefinierte Attribut Klassen. Dadurch wird das Suchen nach dem Attribut beschleunigt.

 *Teile &copy; 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
- [Verwendungs Richtlinien](usage-guidelines.md)
