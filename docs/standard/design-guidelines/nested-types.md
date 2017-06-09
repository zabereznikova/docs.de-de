---
title: "Geschachtelte Typen | Microsoft Docs"
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
  - "geschachtelte Typen"
  - "öffentliche geschachtelte Typen"
  - "Geben Sie Richtlinien für den Entwurf, geschachtelte Typen"
  - "geschachtelte Typen"
  - "[Member [.NET Framework], Typ"
  - "Klassenbibliothek-Entwurf Richtlinien [.NET Framework], geschachtelte Typen"
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Geschachtelte Typen
Ein geschachtelter Typ ist ein Typ, der innerhalb des Gültigkeitsbereichs eines anderen Typs, die den einschließenden Typ aufgerufen wird, definiert. Ein geschachtelter Typ hat Zugriff auf alle Member des einschließenden Typs. Beispielsweise verfügt es über Zugriff auf private Felder definiert, in den einschließenden Typ und geschützte Felder, die in alle Vorgänger des einschließenden Typs definiert.  
  
 Im Allgemeinen sollte nur selten geschachtelte Typen verwendet werden. Hierfür gibt es mehrere Gründe: Einige Entwickler sind nicht vollständig mit dem Konzept vertraut. Diese Entwickler können z. B. Probleme mit der Syntax des Deklarieren von Variablen von geschachtelten Typen haben. Geschachtelte Typen sind ebenfalls sehr eng mit ihren einschließenden Typen verbunden und daher eignen sich nicht um allgemeine Typen sein.  
  
 Geschachtelte Typen eignen sich am besten für die Modellierung von Details zur Implementierung der einschließenden Typen. Der Benutzer sollte nur selten zum Deklarieren von Variablen für einen geschachtelten Typ und fast nie sollte explizit Instanziieren von geschachtelten Typen. Der Enumerator einer Auflistung kann z. B. einen geschachtelten Typ der Auflistung sein. Enumeratoren werden normalerweise von dem einschließenden Typ instanziiert, und da viele Sprachen zu die Foreach\-Anweisung unterstützen Enumerator Variablen selten vom Endbenutzer deklariert werden.  
  
 **✓ führen** geschachtelte Typen verwenden, wenn die Beziehung zwischen den geschachtelten Typ und seinem äußeren Typ ist, sodass Memberzugriff Semantik wünschenswert sind.  
  
 **X nicht** öffentliche geschachtelte Typen als eine logische Gruppierung erstellen, verwenden Sie für diese Namespaces.  
  
 **X vermeiden** öffentlich verfügbar gemacht werden geschachtelte Typen. Die einzige Ausnahme ist, wenn Variablen des geschachtelten Typs müssen nur in seltenen Szenarien wie z. B. Erstellen von Unterklassen oder anderen erweiterten Anpassungsszenarien deklariert werden.  
  
 **X nicht** geschachtelte Typen verwenden, wenn der Typ außerhalb des enthaltenden Typs verwiesen werden kann.  
  
 Eine Enumeration, die an eine Methode für eine Klasse definierten übergeben sollten z. B. nicht als geschachtelter Typ in der Klasse definiert werden.  
  
 **X nicht** geschachtelte Typen verwenden, wenn sie von Clientcode instanziiert werden müssen.  Wenn ein Typ einen öffentlichen Konstruktor verfügt, sollte dieser nicht geschachtelt werden.  
  
 Wenn ein Typ instanziiert werden kann, ist das an, dass der Typ verfügt über einen Ort im Framework selbst erscheint \(Sie können erstellen, arbeiten und zerstören es, ohne jemals mithilfe des äußeren Typs\), und sollte daher nicht geschachtelt werden. Interne Typen sollten nicht häufig wiederverwendet werden außerhalb des äußeren Typs ohne Beziehung ist in den äußeren Typ.  
  
 **X nicht** einen geschachtelten Typ als Member einer Schnittstelle definiert. Dieses Konstrukt wird von vielen Sprachen nicht unterstützt.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)