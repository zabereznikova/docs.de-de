---
title: "Namen von Assemblys und DLLs | Microsoft Docs"
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
  - "[Namen [.NET Framework], DLLs"
  - "[Namen [.NET Framework], Assemblys"
  - "[Assemblys [.NET Framework], Namen"
  - "DLLs, Namen"
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Namen von Assemblys und DLLs
Eine Assembly ist die Einheit der Bereitstellung und Identität für verwalteten Code Programme. Obwohl Assemblys eine oder mehrere Dateien umfassen können, ordnet eine Assembly in der Regel 1: 1 mit einer DLL. Dieser Abschnitt beschreibt daher nur DLL Benennungskonventionen, die dann den Benennungskonventionen der Assembly zugeordnet werden können.  
  
 **✓ führen** Namen für die Assembly\-DLLs, die große Teile der Funktionalität, z. B. "System.Data" vorgeschlagen.  
  
 Assembly\- und DLL\-Namen müssen nicht Namespacenamen entsprechen, aber es ist sinnvoll, den Namen des Namespaces führen beim Benennen von Assemblys. Eine gute Faustregel ist, der basierend auf das gemeinsame Präfix der Assemblys in der Assembly enthaltenen DLL\-name. Angenommen, eine Assembly mit zwei Namespaces `MyCompany.MyTechnology.FirstFeature` und `MyCompany.MyTechnology.SecondFeature`, könnte den Namen `MyCompany.MyTechnology.dll`.  
  
 **✓ ggf.** benennen Sie DLLs nach dem folgenden Muster:  
  
 `<Company>.<Component>.dll`  
  
 wobei `<Component>` enthält eine oder mehrere Klauseln der Punkte getrennt sind. Zum Beispiel:  
  
 `Litware.Controls.dll`.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)