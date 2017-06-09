---
title: "Namespaceunterst&#252;tzung im Dokumentobjektmodell | Microsoft Docs"
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
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Namespaceunterst&#252;tzung im Dokumentobjektmodell
Das XML\-DOM \(Dokumentobjektmodell\) unterstützt Namespaces vollständig.  Es werden nur XML\-Dokumente unterstützt, die mit Namespaces arbeiten können.  Gemäß einer Spezifikation des W3C \(World Wide Web Consortium\) können DOM\-Anwendungen, bei denen Level 1 implementiert ist, Namespaces nicht unterstützen, und DOM\-Funktionen mit Level 2 unterstützen Namespaces.  Alle Funktionen des XML\-DOMs sind jedoch namespacefähig, ungeachtet dessen, ob die Methode aus der Level 1\- oder der Level 2\-Empfehlung stammt.  
  
 Beispielsweise führt das Aufrufen von `setAttribute("A:b", "123")`, wie in der Level 1\-DOM\-Empfehlung spezifiziert, in einer Umgebung, die Namespaces nicht unterstützt, nicht zu einem Attribut mit dem Präfix `A` und dem lokalen Namen `b`.  Vielmehr ergibt der Aufruf ein Attribut mit dem Wert `A:b`.  
  
 In einer namespacefähigen Umgebung führt das Aufrufen von `setAttribute("A:b", "123")` des DOM Level 2 dagegen zu einem Attribut mit dem Präfix `A` und dem lokalen Namen `b`.  So funktioniert das Microsoft .NET Framework\-DOM.  
  
 Daher ist für alle Methoden, die einen Namespaceparameter haben, auch ein Präfix für die Angabe des Names erforderlich.  Der Namensparameter, z. B. `A:b` in der **setAttribute**\-Methode aus dem DOM Level 1, wird wie folgt analysiert:  
  
-   Wenn keine Doppelpunktzeichen \(:\) vorhanden sind, wird für den lokalen Namen der `name`\-Parameter festgelegt, und das Präfix und der **NamespaceURI** sind leere Zeichenfolgen.  
  
-   Wenn Doppelpunkte vorhanden sind, wird der Name gemäß der Position des ersten Doppelpunktzeichens in zwei Abschnitte aufgeteilt.  Als Präfix wird die Zeichenfolge festgelegt, die sich vor dem Doppelpunkt befindet, und als lokaler Name wird die Zeichenfolge festgelegt, die hinter dem Doppelpunkt steht.  Bei Methoden, die keinen **NamespaceURI**\-Wert haben, wird der **NamespaceURI** nicht aufgelöst und bleibt eine leere Zeichenfolge.  Andernfalls wird für den **NamespaceURI** die Zeichenfolge festgelegt, die an die Methode übergeben wird.  Wenn das Präfix nicht definiert ist, schlagen die **Save**\-Methode sowie die **InnerXml**\-Eigenschaft und die **OuterXml**\-Eigenschaft fehl.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)