---
title: Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b2eaf6ccebed38c778e328e34cb6f53177347b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397659"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  In diesem Thema das Verhalten von Assemblys mit starkem Namen behandelt und gelten nur für [Ebene 1](../../../docs/framework/misc/security-transparent-code-level-1.md) Assemblys. [Sicherheitstransparenter Code, Ebene 2](../../../docs/framework/misc/security-transparent-code-level-2.md) Assemblys in der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] oder höher sind von starken Namen nicht betroffen. Weitere Informationen zu Änderungen am Sicherheitssystem finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
 Anwendungen, die kleiner als die volle Vertrauenswürdigkeit vom Host oder Sandkasten dürfen keine gemeinsam genutzten Aufrufen empfangen verwalteten Bibliotheken aus, es sei denn, der Bibliothek hat insbesondere durch Verwendung des ermöglicht die <xref:System.Security.AllowPartiallyTrustedCallersAttribute> Attribut. Anwendungsentwickler müssen daher beachten, dass ihnen aus einem teilweise vertrauenswürdigen Kontext einige Bibliotheken nicht zur Verfügung stehen. Wird standardmäßig der gesamte Code, der ausgeführt wird in einem teilweise vertrauenswürdigen [Sandkasten](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) und nicht in die Liste der vollständig vertrauenswürdigen Assemblys ist, teilweise vertrauenswürdig. Wenn Sie nicht erwarten, dass Ihr Code aus einem teilweise vertrauenswürdigen Kontext heraus ausgeführt oder aus teilweise vertrauenswürdigem Code aufgerufen wird, müssen Sie die Informationen in diesem Abschnitt nicht beachten. Wenn Sie jedoch Code schreiben, der mit teilweise vertrauenswürdigem Code zusammenwirken oder aus einem teilweise vertrauenswürdigen Kontext ausgeführt werden muss, sollten Sie folgende Faktoren berücksichtigen:  
  
-   Bibliotheken müssen mit einem starken Namen signiert sein, damit sie von mehreren Anwendungen gemeinsam genutzt werden können. Starke Namen ermöglichen, dass Ihr Code im globalen Assemblycache platziert oder zur Liste für vollständige Vertrauenswürdigkeit einer Sandkasten-<xref:System.AppDomain> hinzugefügt werden kann, und ermöglichen Kunden festzustellen, dass ein bestimmter Teil mobilen Codes tatsächlich von Ihnen stammt.  
  
-   Standardmäßig mit starken Namen [Ebene 1](../../../docs/framework/misc/security-transparent-code-level-1.md) führen freigegebene Bibliotheken einen impliziten [LinkDemand](../../../docs/framework/misc/link-demands.md) für vollständige Vertrauenswürdigkeit automatisch, ohne dass die Bibliothek nichts zu tun.  
  
-   Wenn ein Aufrufer nicht vollständig vertrauenswürdig ist, aber trotzdem versucht, eine solche Bibliothek aufzurufen, löst die Runtime eine <xref:System.Security.SecurityException> aus, und der Aufrufer kann keine Verbindung mit der Bibliothek herstellen  
  
-   Um die automatische deaktivieren **LinkDemand** und zu verhindern, dass die Ausnahme ausgelöst wird, können Sie platzieren der **AllowPartiallyTrustedCallersAttribute** -Attribut im assemblygültigkeitsbereich einer freigegebenen Bibliothek. Dieses Attribut ermöglicht, dass Ihre Bibliotheken aus teilweise vertrauenswürdigem verwaltetem Code heraus aufgerufen werden können.  
  
-   Teilweise vertrauenswürdiger Code, dem durch dieses Attribut Zugriff auf eine Bibliothek gewährt wird, unterliegt nach wie vor weiteren Beschränkungen, die durch die <xref:System.AppDomain> definiert sind.  
  
-   Es gibt keine programmgesteuerte Möglichkeit für teilweise vertrauenswürdigen Code zum Aufrufen einer Bibliothek, die nicht die **AllowPartiallyTrustedCallersAttribute** Attribut.  
  
 Bibliotheken, die für eine bestimmte Anwendung privat sind, erfordern einen starken Namen oder die **AllowPartiallyTrustedCallersAttribute** Attribut, und kann nicht durch potenziell bösartigen Code außerhalb der Anwendung referenziert werden. Solcher Code ist gegen beabsichtigten oder unbeabsichtigten Missbrauch durch teilweise vertrauenswürdigen mobilen Code geschützt, ohne dass Entwickler zusätzlich aktiv werden müssen.  
  
 Bei folgenden Codetypen sollten Sie in Betracht ziehen, die Verwendung durch teilweise vertrauenswürdigen Code explizit zuzulassen:   
  
-   Code, der sorgfältig auf Sicherheitsrisiken getestet wurde und mit den Richtlinien, die in beschriebenen [Richtlinien für das Schreiben von sicheren Code](../../../docs/standard/security/secure-coding-guidelines.md).  
  
-   Codebibliotheken mit starkem Namen, die speziell für Szenarios geschrieben wurden, in denen teilweise Vertrauenswürdigkeit zu beachten ist.  
  
-   Alle (teilweise oder vollständig vertrauenswürdigen) Komponenten, die mit einem starken Namen signiert sind und von Code aufgerufen werden, der aus dem Internet heruntergeladen wurde.  
  
> [!NOTE]
>  Einige Klassen in der .NET Framework-Klassenbibliothek verfügen nicht über die **AllowPartiallyTrustedCallersAttribute** -Attribut und kann nicht von teilweise vertrauenswürdigem Code aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Codezugriffssicherheit](../../../docs/framework/misc/code-access-security.md)
