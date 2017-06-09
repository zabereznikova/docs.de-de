---
title: "Using Libraries from Partially Trusted Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "security [.NET Framework], partially trusted code"
  - "partially trusted code"
  - "partial trust"
  - "AllowPartiallyTrustedCallersAttribute attribute"
  - "code access security, partially trusted code"
  - "APTCA"
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
caps.latest.revision: 25
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 23
---
# Using Libraries from Partially Trusted Code
> [!NOTE]
>  In diesem Thema wird das Verhalten von Assemblys mit starkem Namen behandelt. Es gilt nur für Assemblys der [Ebene 1](../../../docs/framework/misc/security-transparent-code-level-1.md).[Security\-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md)\-Assemblys in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] oder höher sind von starken Namen nicht betroffen. Weitere Informationen zu Änderungen am Sicherheitssystem finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
> [!CAUTION]
>  Codezugriffssicherheit und teilweise vertrauenswürdiger Code  
>   
>  .NET Framework bietet einen Mechanismus namens Codezugriffssicherheit \(Code Access Security, CAS\) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.  Sie sollten die Codezugriffssicherheit in .NET Framework nicht als Sicherheitsbegrenzung bei teilweise vertrauenswürdigem Code verwenden. Dies gilt insbesondere für Code unbekannter Herkunft. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.  
>   
>  Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework\-Version.  
  
 Anwendungen, die vom Host oder Sandkasten keine vollständige Vertrauenswürdigkeit erhalten, dürfen keine gemeinsam verwendeten verwalteten Bibliotheken aufrufen, es sei denn, der Entwickler der Bibliothek hat dies ausdrücklich durch Verwenden des <xref:System.Security.AllowPartiallyTrustedCallersAttribute>\-Attributs zugelassen. Anwendungsentwickler müssen daher beachten, dass ihnen aus einem teilweise vertrauenswürdigen Kontext einige Bibliotheken nicht zur Verfügung stehen. Standardmäßig ist der gesamte Code, der in einem teilweise vertrauenswürdigen [Sandkasten](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) ausgeführt wird und nicht in der Liste der voll vertrauenswürdigen Assemblys aufgeführt ist, teilweise vertrauenswürdig. Wenn Sie nicht erwarten, dass Ihr Code aus einem teilweise vertrauenswürdigen Kontext heraus ausgeführt oder aus teilweise vertrauenswürdigem Code aufgerufen wird, müssen Sie die Informationen in diesem Abschnitt nicht beachten. Wenn Sie jedoch Code schreiben, der mit teilweise vertrauenswürdigem Code zusammenwirken oder aus einem teilweise vertrauenswürdigen Kontext ausgeführt werden muss, sollten Sie folgende Faktoren berücksichtigen:  
  
-   Bibliotheken müssen mit einem starken Namen signiert sein, damit sie von mehreren Anwendungen gemeinsam genutzt werden können. Starke Namen ermöglichen, dass Ihr Code im globalen Assemblycache platziert oder zur Liste für vollständige Vertrauenswürdigkeit einer Sandkasten\-<xref:System.AppDomain> hinzugefügt werden kann, und ermöglichen Kunden festzustellen, dass ein bestimmter Teil mobilen Codes tatsächlich von Ihnen stammt.  
  
-   Standardmäßig führen mit starkem Namen versehene gemeinsam genutzte [Ebene 1](../../../docs/framework/misc/security-transparent-code-level-1.md)\-Bibliotheken automatisch einen impliziten [LinkDemand](../../../docs/framework/misc/link-demands.md) für vollständige Vertrauenswürdigkeit aus, ohne dass der Entwickler der Bibliothek aktiv werden muss.  
  
-   Wenn ein Aufrufer nicht vollständig vertrauenswürdig ist, aber trotzdem versucht, eine solche Bibliothek aufzurufen, löst die Runtime eine <xref:System.Security.SecurityException> aus, und der Aufrufer kann keine Verbindung mit der Bibliothek herstellen  
  
-   Um das automatische **LinkDemand** zu deaktivieren und zu verhindern, dass die Ausnahme ausgelöst wird, können Sie das **AllowPartiallyTrustedCallersAttribute**\-Attribut im Assemblygültigkeitsbereich einer gemeinsam genutzten Bibliothek platzieren. Dieses Attribut ermöglicht, dass Ihre Bibliotheken aus teilweise vertrauenswürdigem verwaltetem Code heraus aufgerufen werden können.  
  
-   Teilweise vertrauenswürdiger Code, dem durch dieses Attribut Zugriff auf eine Bibliothek gewährt wird, unterliegt nach wie vor weiteren Beschränkungen, die durch die <xref:System.AppDomain> definiert sind.  
  
-   Für teilweise vertrauenswürdigen Code gibt es keine programmgesteuerte Möglichkeit zum Aufrufen einer Bibliothek, die nicht das **AllowPartiallyTrustedCallersAttribute**\-Attribut hat.  
  
 Bibliotheken, die für eine bestimmte Anwendung privat sind, erfordern keinen starken Namen oder das **AllowPartiallyTrustedCallersAttribute**\-Attribut, und es ist nicht möglich, durch potenziell bösartigen Code außerhalb der Anwendung auf sie zu verweisen. Solcher Code ist gegen beabsichtigten oder unbeabsichtigten Missbrauch durch teilweise vertrauenswürdigen mobilen Code geschützt, ohne dass Entwickler zusätzlich aktiv werden müssen.  
  
 Bei folgenden Codetypen sollten Sie in Betracht ziehen, die Verwendung durch teilweise vertrauenswürdigen Code explizit zuzulassen:  
  
-   Code, der sorgfältig auf Sicherheitsrisiken getestet wurde und mit den Regeln übereinstimmt, die unter [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md) beschrieben werden.  
  
-   Codebibliotheken mit starkem Namen, die speziell für Szenarios geschrieben wurden, in denen teilweise Vertrauenswürdigkeit zu beachten ist.  
  
-   Alle \(teilweise oder vollständig vertrauenswürdigen\) Komponenten, die mit einem starken Namen signiert sind und von Code aufgerufen werden, der aus dem Internet heruntergeladen wurde.  
  
> [!NOTE]
>  Einige in der .NET Framework\-Klassenbibliothek enthaltene Klassen haben nicht das **AllowPartiallyTrustedCallersAttribute**\-Attribut und können nicht von teilweise vertrauenswürdigem Code aufgerufen werden.  
  
## Siehe auch  
 [Code Access Security](../../../docs/framework/misc/code-access-security.md)