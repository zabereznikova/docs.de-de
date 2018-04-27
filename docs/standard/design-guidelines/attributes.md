---
title: Attributes1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c169586091f0e7e094e0231f9e247e8907371ec4
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="attributes"></a>Attribute
<xref:System.Attribute?displayProperty=nameWithType> eine Basisklasse wird zum Definieren von benutzerdefinierter Attributen verwendet werden.  
  
 Attribute sind Anmerkungen, die um Programmierelemente wie Assemblys, Typen, Member und Parameter hinzugefügt werden können. Sie werden in den Metadaten der Assembly gespeichert und zur Laufzeit mit der Reflektions-APIs zugegriffen werden können. Das Framework definiert z. B. die <xref:System.ObsoleteAttribute>, die auf einen Typ oder ein Element aus, um anzugeben, dass der Typ oder Member veraltet ist angewendet werden können.  
  
 Attribute können eine oder mehrere Eigenschaften aufweisen, die zusätzliche Daten, die im Zusammenhang mit dem Attribut enthalten. Beispielsweise `ObsoleteAttribute` konnte enthalten zusätzliche Informationen über die Freigabe in der ein Typ oder Member veraltet erhalten haben und die Beschreibung der neuen APIs ersetzt die veraltete API.  
  
 Einige Eigenschaften eines Attributs müssen angegeben werden, wenn das Attribut angewendet wird. Diese sind als die erforderlichen Eigenschaften oder die erforderlichen Argumente bezeichnet, da sie als Konstruktorparameter mit Feldern fester Breite dargestellt werden. Z. B. die <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> Eigenschaft von der <xref:System.Diagnostics.ConditionalAttribute> ist eine erforderliche Eigenschaft.  
  
 Eigenschaften, die nicht unbedingt angegeben werden, wenn das Attribut angewendet wird, werden optionale Eigenschaften (oder optionale Argumente) bezeichnet. Sie werden durch festlegbaren Eigenschaften dargestellt. Compiler bieten spezielle Syntax, um diese Eigenschaften festzulegen, wenn ein Attribut angewendet wird. Z. B. die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> Eigenschaft darstellt, ein optionales Argument.  
  
 **Führen Sie ✓** benennen Sie benutzerdefinierte Attributklassen mit dem Suffix "-Attribut" an.  
  
 **Führen Sie ✓** gelten die <xref:System.AttributeUsageAttribute> zu benutzerdefinierten Attributen.  
  
 **Führen Sie ✓** festlegbare Eigenschaften bereitstellen, für die optionalen Argumente.  
  
 **Führen Sie ✓** nur Get-Eigenschaften für die erforderlichen Argumente bereitstellen.  
  
 **Führen Sie ✓** Konstruktorparameter zum Initialisieren der Eigenschaften, die erforderlichen Argumente bereitstellen. Jeder Parameter muss den gleichen Namen (obwohl mit abweichender Groß-/Kleinschreibung) als die entsprechende Eigenschaft verfügen.  
  
 **X vermeiden** Konstruktorparameter zum Initialisieren der Eigenschaften, die die optionalen Argumente bereitstellen.  
  
 Das heißt, keine Eigenschaften, die mit einem Konstruktor und einen Setter festgelegt werden können. Diese Richtlinie stellt sehr explizite, welche Argumente optional sind und die erforderlich sind, und vermeidet zwei Möglichkeiten, auf diese Weise dieselbe Bedeutung.  
  
 **X vermeiden** Überladen von Konstruktoren des benutzerdefinierten Attributs.  
  
 Nur über einen Konstruktor mit kommuniziert eindeutig für den Benutzer die Argumente erforderlich sind und welche optional sind.  
  
 **Führen Sie ✓** versiegeln Sie benutzerdefinierte Attributklassen, falls möglich. Dies beschleunigt die Suchregeln für das Attribut.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
