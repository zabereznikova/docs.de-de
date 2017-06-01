---
title: "Feldentwurf | Microsoft Docs"
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
  - "Felder, Entwurfsrichtlinien"
  - "schreibgeschützte Felder"
  - "Entwurfsrichtlinien für Member, Felder"
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Feldentwurf
Das Prinzip der Kapselung ist eines der wichtigsten Konzepte in objektorientierten Entwurf. Dieses Prinzip besagt, dass in einem Objekt gespeicherte Daten nur auf das Objekt zugegriffen werden soll.  
  
 Eine gute Möglichkeit, das Prinzip zu interpretieren ist zu sagen, dass ein Typ sollten so konzipiert sein, dass Felder dieses Typs \(Name oder Typ ändert\) geändert werden kann, ohne dass Code nur für Member des Typs unterbrochen. Diese Interpretation impliziert sofort, dass alle Felder privat sein müssen.  
  
 Wir ausschließen Konstanten und statische schreibgeschützte Felder aus dieser Einschränkung strenge, da solche Felder per Definition fast nie erforderlich sind ändern.  
  
 **X nicht** die öffentliche oder geschützte Instanzfelder bereit.  
  
 Für den Zugriff auf Felder anstelle von öffentlichen oder geschützten somit sollten Sie die Eigenschaften bereitstellen.  
  
 **✓ führen** verwenden Sie Konstante Felder für Konstanten, die nie geändert wird.  
  
 Der Compiler brennt die Werte der Konstanten Felder direkt in Code aufrufen. Konstante Werte können daher nicht ohne das Risiko der Unterbrechung Kompatibilität geändert werden.  
  
 **✓ führen** öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen.  
  
 Deklarieren sie vordefinierte Instanzen des Typs vorhanden sind, als öffentliche schreibgeschützte statische Felder des Typs selbst.  
  
 **X nicht** zuweisen Instanzen änderbarer Typen zu `readonly` Felder.  
  
 Ein änderbarer Typ ist ein Typ mit den Instanzen, die geändert werden können, nachdem sie instanziiert werden. Z. B. Arrays, die meisten Sammlungen und Streams änderbarer Typen sind jedoch <xref:System.Int32?displayProperty=fullName>, <xref:System.Uri?displayProperty=fullName>, und <xref:System.String?displayProperty=fullName> Alle unveränderlich sind. Die schreibgeschützten Modifizierer auf einen Typ Referenzfeld wird verhindert, dass die Instanz im Feld ersetzt wird, aber es verhindert nicht, dass Instanzdaten des Felds geändert wird, durch Aufruf von Membern die Instanz ändern.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)