---
title: "Namespaces und DTDs im DOM | Microsoft Docs"
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
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Namespaces und DTDs im DOM
DTDs \(Document Type Definition\) erschweren die Namespace\-Unterstützung.  Das folgende XML\-Beispiel enthält Standardattribute, deren Namen Doppelpunkte enthalten.  
  
```  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 Folgende Auflösungen sind möglich, wenn dieses Konstrukt zulässig ist:  
  
-   `x:` wird als Namespacepräfix behandelt, aber dieses Präfix muss mit einer `xmlns:x`\-Namespacedeklaration auflösbar sein, die auch an einer beliebigen Stelle in der DTD vorhanden sein muss.  Wenn das Präfix einem anderen Element im Instanzdokument zugeordnet wird, stellt dies einen Fehler dar.  
  
-   `x:` wird als Namespacepräfix behandelt, aber dieses Präfix wird immer im Kontext der Instanzelemente aufgelöst.  Das bedeutet, dass das Präfix im Grunde verschiedenen Namespace\-URIs \(Uniform Resource Identifier\) zugeordnet werden könnte, je nachdem, in welchem Namespacegültigkeitsbereich das `item`\-Element auftritt.  Dieses Verhalten ist besser vorhersagbar als die im vorherigen Punkt beschriebene Auflösung; es hat jedoch andere komplizierte Auswirkungen, da es erfordert, dass die Standardattribute materialisiert werden.  
  
-   Der Doppelpunkt wird ignoriert, da er in einer DTD vorkommt, und der Name des Attributs ist `x:y`. Es ist kein Präfix und kein Namespace\-URI vorhanden.  
  
-   Der Doppelpunkt im Standardattribut löst eine Ausnahme aus, die besagt, dass Doppelpunkte in Namen innerhalb einer DTD nicht unterstützt werden.  Dies führt zu einem vorhersagbaren Verhalten, bedeutet aber auch, dass Sie nur einige der vom W3C \(World Wide Web Consortium\) veröffentlichten DTDs laden können.  
  
-   Wenn der Benutzer eine DTD\-Validierung anfordert, wird die Unterstützung von Namespaces für das gesamte Dokument deaktiviert.  Dadurch können W3C\-DTDs geladen werden, und es ergibt sich ein vorhersagbares Verhalten.  
  
 Beim XML\-Code in .NET Framework wird die zweite Option implementiert, um maximale Kompatibilität mit der W3C\-Spezifikation zu gewährleisten.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)