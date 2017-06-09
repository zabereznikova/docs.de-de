---
title: "Eigenschaftenentwurf | Microsoft Docs"
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
  - "Entwurfsrichtlinien für Member, Eigenschaften"
  - "[Eigenschaften [.NET Framework], Entwurfsrichtlinien"
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Eigenschaftenentwurf
Obwohl Eigenschaften, Methoden technisch sehr ähnlich sind, sind sie in Bezug auf ihre Szenarios für die Verwendung sehr unterschiedlich. Sie sollte als intelligente Felder angezeigt werden. Sie haben die Aufrufsyntax von Feldern und der Flexibilität der Methoden.  
  
 **✓ führen** schreibgeschützte Eigenschaften erstellen, wenn der Aufrufer nicht der Wert der Eigenschaft geändert werden soll.  
  
 Bedenken Sie, dass bei den Typ der Eigenschaft einen änderbaren Referenztyp ist, den Wert der Eigenschaft geändert werden kann, selbst wenn die Eigenschaft nur.  
  
 **X nicht** lesegeschützte Eigenschaften oder Eigenschaften mit dem Setter mit umfassenderen Zugriff als Getter\-Methode bereitstellen.  
  
 Verwenden Sie z. B. Eigenschaften nicht mit einem öffentlichen Setter und eine geschützte Getter.  
  
 Wenn der Eigenschaftengetter nicht bereitgestellt werden kann, implementieren Sie stattdessen die Funktion als Methode. Möglicherweise sollten Sie den Namen der Methode mit `Set` und mit was Sie die Eigenschaft benannt haben würde. Z. B. <xref:System.AppDomain> eine Methode namens `SetCachePath` anstatt eine lesegeschützte Eigenschaft mit dem Namen `CachePath`.  
  
 **✓ führen** bieten sinnvolle Standardwerte für alle Eigenschaften, um sicherzustellen, dass die Standardwerte nicht in eine Sicherheitslücke oder furchtbar ineffizient Code führen.  
  
 **✓ führen** können Eigenschaften in einer beliebigen Reihenfolge festgelegt werden, auch wenn dies in einem temporären ungültigen Zustand des Objekts.  
  
 Es ist üblich, dass zwei oder mehr Eigenschaften zu einem Zeitpunkt zusammenhängender sein, in denen einige Werte einer Eigenschaft möglicherweise ungültig, angegebenen Werte anderer Eigenschaften für das gleiche Objekt. In solchen Fällen sollten Ausnahmen, die durch einen ungültigen Zustand verschoben werden, bis die zusammenhängenden Eigenschaften durch das Objekt tatsächlich zusammen verwendet werden.  
  
 **✓ führen** den vorherigen Wert beibehalten, wenn ein Eigenschaftensetter eine Ausnahme auslöst.  
  
 **X vermeiden** Auslösen von Ausnahmen von Eigenschaftengetter.  
  
 Eigenschaftengetter sollte sollten einfache Operationen sein und keiner Preconditions. Wenn eine Get\-Methode eine Ausnahme auslösen kann, müssen sie möglicherweise eine Methode überarbeitet werden. Beachten Sie, dass diese Regel nicht für Indexer ist gilt, in dem wir Ausnahmen durch Überprüfen der Argumente erwarten.  
  
### Entwurf indizierter Eigenschaften  
 Eine indizierte Eigenschaft ist eine spezielle Eigenschaft, die Parameter und kann mit speziellen Syntax ähnelt Arrayindizierung aufgerufen werden.  
  
 Indizierte Eigenschaften werden häufig als Indexer bezeichnet. Indexer sollte nur in APIs verwendet werden, die Zugriff auf Elemente in einer logischen Auflistung bereitstellen. Z. B. eine Zeichenfolge ist eine Auflistung von Zeichen und der Indexer auf <xref:System.String?displayProperty=fullName> wurde hinzugefügt, um Zugriff auf die Zeichen.  
  
 **✓ ggf.** mithilfe von Indexern Zugriff auf Daten in einem internen Array gespeichert.  
  
 **✓ ggf.** Indexer auf Typen, die Auflistungen von Elementen bereitstellen.  
  
 **X vermeiden** mithilfe von indizierten Eigenschaften mit mehreren Parametern.  
  
 Wenn der Entwurf mehrere Parameter erfordert, überprüfen Sie, ob die Eigenschaft einen Accessor tatsächlich auf eine logische Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie stattdessen Methoden. Möglicherweise sollten Sie den Namen der Methode mit `Get` oder `Set`.  
  
 **X vermeiden** Indexer mit Parametertypen außer <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.String?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, oder eine Enumeration.  
  
 Wenn der Entwurf andere Parametertypen erfordert, stark auswertet, ob die API einen Accessor tatsächlich auf eine logische Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie eine Methode. Möglicherweise sollten Sie den Namen der Methode mit `Get` oder `Set`.  
  
 **✓ führen** verwenden Sie den Namen `Item` für indizierte Eigenschaften, es sei denn, es kein offensichtlich geeigneterer Name ist \(z. B. finden Sie unter der <xref:System.String.Chars%2A> Eigenschaft `System.String`\).  
  
 Sind C\#\-Indexer standardmäßig mit dem Namen Item. Die <xref:System.Runtime.CompilerServices.IndexerNameAttribute> kann zum Anpassen dieser Name verwendet werden.  
  
 **X nicht** bieten einen Indexer und Methoden, die semantisch ähnlich sind.  
  
 **X nicht** bieten mehr als eine Gruppe überladener Indexer in einem Typ.  
  
 Dies wird vom C\#\-Compiler erzwungen.  
  
 **X nicht** Verwendung nicht standardmäßiger indizierte Eigenschaften.  
  
 Dies wird vom C\#\-Compiler erzwungen.  
  
### Property Change Notification Events  
 Manchmal ist es sinnvoll, ein Ereignis, das der Benutzer Änderungen eines Eigenschaftswerts bereitstellen. Z. B. `System.Windows.Forms.Control` löst ein `TextChanged` Ereignis nach dem Wert der `Text` \-Eigenschaft geändert hat.  
  
 **✓ ggf.** auslösen ändern Benachrichtigungsereignisse, wenn Eigenschaftswerte in APIs hoher Ebene \(normalerweise Designer\-Komponenten\) geändert werden.  
  
 Ist eine gute Szenario für einen Benutzer wissen, wenn eine Eigenschaft eines Objekts geändert wird, sollte das Objekt ein Änderungsereignis für die Eigenschaft auszulösen.  
  
 Allerdings ist es unwahrscheinlich, sollte der Mehraufwand für Low\-Level\-APIs wie z. B. Basistypen oder Sammlungen solche Ereignisse ausgelöst werden. Z. B. <xref:System.Collections.Generic.List%601> würde nicht auslösen, solche Ereignisse, wenn der Liste ein neues Element hinzugefügt wird und die `Count` \-Eigenschaft ändert.  
  
 **✓ ggf.** auslösen Benachrichtigungsereignisse, wenn der Wert einer Eigenschaft über externe erzwingt ändert ändern.  
  
 Wenn die Änderung eines Eigenschaftswerts über einige externe erzwingen \(in einer Weise als durch Aufrufen von Methoden für das Objekt\) löst Ereignisse angegeben werden, der Entwickler, dass der Wert und hat sich geändert. Ein gutes Beispiel ist die `Text` Eigenschaft für ein Textfeld\-Steuerelement. Wenn der Benutzer Text eingibt ein `TextBox`, automatisch den Wert der Eigenschaft ändert.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)