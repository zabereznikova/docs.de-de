---
title: "Attributes1 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Attribute [.NET Framework] zu"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Attribute"
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# Attribute
<xref:System.Attribute?displayProperty=fullName> eine Basisklasse ist zum Definieren von benutzerdefinierter Attributen verwendet.  
  
 Attribute sind Anmerkungen, die auf Programmierelemente, z. B. Assemblys, Typen, Member und Parameter hinzugefügt werden können. Sie werden in den Metadaten der Assembly gespeichert und können zur Laufzeit mithilfe der Reflektions\-APIs zugegriffen werden. Das Framework definiert z. B. die <xref:System.ObsoleteAttribute>, auf einen Typ oder einen Member, um anzugeben, dass der Typ oder Member veraltet ist angewendet werden können.  
  
 Attribute können eine oder mehrere Eigenschaften haben, die zusätzliche Daten, die im Zusammenhang mit dem Attribut enthalten. Z. B. `ObsoleteAttribute` könnte natürlich zusätzliche Informationen zur Version in der ein Typ oder Member veraltet ist und die Beschreibung der neuen APIs ersetzt die API veraltete.  
  
 Einige Eigenschaften eines Attributs müssen angegeben werden, wenn das Attribut angewendet wird. Diese sind als die erforderlichen Eigenschaften oder die erforderlichen Argumente bezeichnet, da sie als Konstruktorparameter mit Feldern fester Breite dargestellt werden. Zum Beispiel die <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> Eigenschaft der <xref:System.Diagnostics.ConditionalAttribute> ist eine erforderliche Eigenschaft.  
  
 Eigenschaften, die nicht unbedingt angegeben werden, wenn das Attribut angewendet wird, werden optionale Eigenschaften \(oder optionalen Argumenten\) bezeichnet. Sie werden durch konfigurierbare Eigenschaften dargestellt. Compiler bieten spezielle Syntax, um diese Eigenschaften festzulegen, wenn ein Attribut angewendet wird. Zum Beispiel die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=fullName> Eigenschaft ein optionales Argument darstellt.  
  
 **✓ führen** Namen benutzerdefinierte Attributklassen mit dem Suffix "\-Attribut".  
  
 **✓ führen** gelten die <xref:System.AttributeUsageAttribute> auf benutzerdefinierte Attribute.  
  
 **✓ führen** festlegbare Eigenschaften für optionale Argumente bereitstellen.  
  
 **✓ führen** schreibgeschützte Eigenschaften für die erforderlichen Argumente angeben.  
  
 **✓ führen** Konstruktorparameter zum Initialisieren der Eigenschaften, die erforderlichen Argumente angeben. Jeder Parameter muss den gleichen Namen wie die entsprechende Eigenschaft \(jedoch mit einer anderen Schreibweise\) besitzen.  
  
 **X vermeiden** Konstruktorparameter zum Initialisieren der Eigenschaften, die die optionalen Argumente bereitstellen.  
  
 Das heißt, keine Eigenschaften, die mit einem Konstruktor und einen Setter festgelegt werden können. Diese Richtlinie ist sehr deutlich, welche Argumente optional sind und die erforderlich sind, und vermeiden Sie, dass zwei Möglichkeiten, die gleiche Weise.  
  
 **X vermeiden** benutzerdefinierte Attributkonstruktoren überladen.  
  
 Nur über einen Konstruktor mit kommuniziert eindeutig für den Benutzer welche Argumente erforderlich sind und welche optional sind.  
  
 **✓ führen** versiegeln Sie benutzerdefinierte Attributklassen, falls möglich. Dies beschleunigt die Suche für das Attribut.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)