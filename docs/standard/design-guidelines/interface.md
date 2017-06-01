---
title: "Entwurf der Benutzeroberfl&#228;che | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "[Schnittstellen [.NET Framework], Entwurfsrichtlinien"
  - "Typentwurfsrichtlinien Schnittstellen"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Schnittstellen"
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Entwurf der Benutzeroberfl&#228;che
Die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, es gibt jedoch Fälle, in denen Schnittstellen sind besser geeignet, oder die einzige Option.  
  
 Die CLR unterstützt keine mehrfache Vererbung \(d. h. CLR\-Klassen aus mehr als einer Basisklasse erben nicht möglich\), jedoch Typen eine oder mehrere Schnittstellen neben der von einer Basisklasse erben. Schnittstellen werden daher häufig verwendet, um mehrfache Vererbung zu unterbinden. Z. B. <xref:System.IDisposable> ist eine Schnittstelle, über die Typen, die unabhängig von jedem anderen Vererbungshierarchie Disposability unterstützen, in dem sie teilnehmen möchten.  
  
 Das andere Szenario, in der, das Definition eine Schnittstelle geeignet ist, ist in eine gemeinsame Schnittstelle, die von unterschiedlichen Typs, darunter einige Werttypen unterstützt werden können. Werttypen nicht von Typen erben, außer <xref:System.ValueType>, jedoch können Schnittstellen implementieren, also mit einer Schnittstelle ist die einzige Option, um einen allgemeinen Basistyp bereitzustellen.  
  
 **✓ führen** eine Schnittstelle definieren, sollten Sie einige allgemeine API durch einen Satz von Typen unterstützt werden, die Werttypen enthält.  
  
 **✓ ggf.** eine Schnittstelle definiert, wenn Sie ihre Funktionalität für Typen zu unterstützen, die bereits von einem anderen Typ erben müssen.  
  
 **X vermeiden** mithilfe der Markerschnittstellen \(Schnittstellen ohne Member\).  
  
 Wenn eine Klasse als ein bestimmtes Merkmal \(Marker\) markiert werden sollen, verwenden Sie im Allgemeinen ein benutzerdefiniertes Attribut anstelle einer Schnittstelle.  
  
 **✓ führen** Geben Sie mindestens einen Typ, die Implementierung einer Schnittstelle.  
  
 Dies erleichtert den Entwurf der Schnittstelle zu überprüfen. Z. B. <xref:System.Collections.Generic.List%601> ist eine Implementierung der <xref:System.Collections.Generic.IList%601> Schnittstelle.  
  
 **✓ führen** Geben Sie mindestens eine API, die jede Schnittstelle nutzt Sie definieren \(eine Methode, die die Schnittstelle als Parameter oder einer Eigenschaft annimmt, die als Schnittstelle eingegeben wird\).  
  
 Dies erleichtert den Entwurf der Benutzeroberfläche zu überprüfen. Z. B. <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=fullName> nutzt die <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> Schnittstelle.  
  
 **X nicht** Hinzufügen von Mitgliedern zu einer Schnittstelle, die bereits veröffentlicht wurden.  
  
 Dadurch würde die Implementierung der Schnittstelle ausgesetzt. Erstellen Sie eine neue Schnittstelle, um Versionsprobleme zu vermeiden.  
  
 Außer in diesen Richtlinien beschriebenen Situationen sollte im allgemeinen Klassen statt Schnittstellen wählen Sie in Design wiederverwendbarer Bibliotheken von verwaltetem Code.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)