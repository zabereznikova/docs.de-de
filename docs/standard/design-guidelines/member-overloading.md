---
title: "&#220;berladen von Membern | Microsoft Docs"
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
  - "Standardargumente"
  - "[Member [.NET Framework], überladen"
  - "Entwurfsrichtlinien für Member [.NET Framework], überladen"
  - "Überladene Member"
  - "Signaturen, Mitglieder"
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;berladen von Membern
Überladen von Membern bedeutet das Erstellen von zwei oder mehr Elemente auf dem gleichen Typ, die den gleichen Namen haben, unterscheiden sich nur hinsichtlich der Anzahl oder Typ der Parameter. Z. B. im folgenden die `WriteLine` \-Methode ist überladen:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
  
```  
  
 Da nur Methoden, Konstruktoren und indizierte Eigenschaften\-Parameter verfügen, können nur die Member überladen werden.  
  
 Überladen ist eines der wichtigsten Verfahren zum Verbessern der Verwendbarkeit, Produktivität und die Lesbarkeit von wieder verwendbaren Bibliotheken. Überladen für die Anzahl von Parametern ermöglicht die einfachere Versionen der Konstruktoren und Methoden bereitstellen. Überladen für den Parametertyp vereinfacht den gleichen Membernamen für Elemente, die identische Vorgänge für eine ausgewählte Gruppe verschiedener Typen verwenden.  
  
 **✓ führen** beschreibende Parameternamen verwenden an, dass vom kürzeren Überladungen als Standardwert verwendet.  
  
 **X vermeiden** willkürlich unterschiedliche Parameternamen in Überladungen. Wenn ein Parameter in einer Überladung dieselbe Eingabe als Parameter in einer anderen Überladung darstellt, sollte der Parameter den gleichen Namen aufweisen.  
  
 **X vermeiden** Mitglieder überlastet werden in der Reihenfolge der Parameter im inkonsistent. Parameter mit dem gleichen Namen in der gleichen Position in alle Überladungen angezeigt.  
  
 **✓ führen** machen die längste Überladung nur virtuell \(wenn Erweiterbarkeit erforderlich ist\). Kürzere Überladungen sollte über eine längere Überladung aufrufen.  
  
 **X nicht** verwenden `ref` oder `out` Modifizierer zum Überladen von Membern.  
  
 Einige Sprachen nicht Aufrufe Überladungen wie folgt aufgelöst. Darüber hinaus sollte solche Überladungen normalerweise völlig andere Semantik und wahrscheinlich nicht Überladungen jedoch zwei separate Methoden stattdessen.  
  
 **X nicht** verfügen über Überladungen mit Parametern, die an der gleichen Position und ähnliche Typen noch mit einer anderen Semantik.  
  
 **✓ führen**  ermöglichen `null` für optionale Argumente übergeben werden soll.  
  
 **✓ führen** verwenden Member überladen, statt Member mit Standardargumenten zu definieren.  
  
 Standardargumente sind nicht CLS\-kompatibel.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)