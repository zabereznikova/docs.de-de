---
title: "Versiegeln | Microsoft Docs"
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
  - "Beschränken der Erweiterbarkeit"
  - "[Klassen [.NET Framework], versiegeln"
  - "Verhindern der Anpassung"
  - "Versiegelte Klassen"
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Versiegeln
Eines der Features von objektorientierten Frameworks ist, dass Entwickler auf unvorhergesehene durch die Framework\-Entwickler Weise anpassen und erweitern können. Dies ist die Leistungsfähigkeit und die Gefahr eines erweiterbaren Entwurf. Wenn Sie Ihr Framework entwerfen, es ist daher sehr wichtig für die Erweiterbarkeit sorgfältig entworfen wird, wenn es gewünscht wird, und Erweiterbarkeit zu beschränken, wenn es gefährlich sein kann.  
  
 Eine leistungsstarke Möglichkeit, Erweiterbarkeit ist versiegeln. Sie können die Klasse oder die einzelnen Mitglieder versiegeln. Versiegelns einer Klasse wird verhindert, dass Benutzer von der\-Klasse erben. Versiegeln ein Element wird verhindert, dass Benutzer einen bestimmten Member zu überschreiben.  
  
 **X nicht** versiegeln Sie Klassen ohne einen guten Grund dafür.  
  
 Versiegelns einer Klasse, da Sie ein Szenario Erweiterbarkeit einfällt ist keinen guten Grund. Framework\-Benutzer wie aus verschiedenen Gründen nonobvious wie das Hinzufügen der Einfachheit halber Member von Klassen erben. Finden Sie unter [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md) für Beispiele für Gründe für nonobvious Benutzer von einem Typ erben soll.  
  
 Gute Gründe für Versiegelns einer Klasse umfassen Folgendes:  
  
-   Die\-Klasse ist eine statische Klasse. Siehe [Entwurf statischer Klassen](../../../docs/standard/design-guidelines/static-class.md).  
  
-   Die Klasse speichert vertrauliche geheime Schlüssel in geerbte geschützte Member.  
  
-   Die Klasse erbt zahlreiche virtuelle Member, und die Kosten für diese einzeln versiegeln würde überwiegen die Vorteile der Klasse nicht versiegelt.  
  
-   Die Klasse ist ein Attribut, das sehr schnelle Common Language Runtime\-Suche erfordert. Versiegelte Attribute haben etwas mehr Leistung als nicht versiegeltes. Siehe [Attribute](../../../docs/standard/design-guidelines/attribute.md).  
  
 **X nicht** geschützten oder virtuellen Member in versiegelten Typen deklarieren.  
  
 Per Definition können von versiegelte Typen geerbt werden. Dies bedeutet, dass geschützte Member in versiegelten Typen nicht aufgerufen werden, und virtuelle Methoden in versiegelten Typen nicht überschrieben werden.  
  
 **✓ ggf.** versiegeln Member, die Sie außer Kraft setzen.  
  
 Probleme, die entstehen können, Einführung in virtuelle Member \(beschrieben [Virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)\) überschreibt, auch in etwas geringerem Maß zuweisen. Versiegeln einer Außerkraftsetzung schützt Sie vor solchen Problemen, die von diesem Punkt in der Vererbungshierarchie ab.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md)