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
ms.openlocfilehash: 6d858ef4c2f70c55b0a36e845f90d9a8e08f5e2d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487821"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  In diesem Thema behandelt das Verhalten von Assemblys mit starkem Namen und gilt nur für [auf Ebene 1](../../../docs/framework/misc/security-transparent-code-level-1.md) Assemblys. [Sicherheitstransparenter Code, Ebene 2](../../../docs/framework/misc/security-transparent-code-level-2.md) Assemblys in .NET Framework 4 oder höher sind von starken Namen nicht betroffen. Weitere Informationen zu Änderungen am Sicherheitssystem finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
 Anwendungen, die vom Host oder Sandkasten keine vollständige Vertrauenswürdigkeit erhalten, dürfen keine gemeinsam verwendeten verwalteten Bibliotheken aufrufen, es sei denn, der Entwickler der Bibliothek hat dies ausdrücklich durch Verwenden des <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attributs zugelassen. Anwendungsentwickler müssen daher beachten, dass ihnen aus einem teilweise vertrauenswürdigen Kontext einige Bibliotheken nicht zur Verfügung stehen. In der Standardeinstellung alle, die codeausführung in einer teilweise vertrauenswürdigen [Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) und nicht in die Liste der vollständig vertrauenswürdigen Assemblys teilweise vertrauenswürdig ist. Wenn Sie nicht erwarten, dass Ihr Code aus einem teilweise vertrauenswürdigen Kontext heraus ausgeführt oder aus teilweise vertrauenswürdigem Code aufgerufen wird, müssen Sie die Informationen in diesem Abschnitt nicht beachten. Wenn Sie jedoch Code schreiben, der mit teilweise vertrauenswürdigem Code zusammenwirken oder aus einem teilweise vertrauenswürdigen Kontext ausgeführt werden muss, sollten Sie folgende Faktoren berücksichtigen:  
  
- Bibliotheken müssen mit einem starken Namen signiert sein, damit sie von mehreren Anwendungen gemeinsam genutzt werden können. Starke Namen ermöglichen, dass Ihr Code im globalen Assemblycache platziert oder zur Liste für vollständige Vertrauenswürdigkeit einer Sandkasten-<xref:System.AppDomain> hinzugefügt werden kann, und ermöglichen Kunden festzustellen, dass ein bestimmter Teil mobilen Codes tatsächlich von Ihnen stammt.  
  
- In der Standardeinstellung starkem [auf Ebene 1](../../../docs/framework/misc/security-transparent-code-level-1.md) freigegebene Bibliotheken führen Sie ein implizites [LinkDemand](../../../docs/framework/misc/link-demands.md) für vollständige Vertrauenswürdigkeit automatisch, ohne Sie zu der Bibliothek hat, müssen nichts weiter tun.  
  
- Wenn ein Aufrufer nicht vollständig vertrauenswürdig ist, aber trotzdem versucht, eine solche Bibliothek aufzurufen, löst die Runtime eine <xref:System.Security.SecurityException> aus, und der Aufrufer kann keine Verbindung mit der Bibliothek herstellen  
  
- Zum Deaktivieren der automatischen **LinkDemand** und zu verhindern, dass die Ausnahme ausgelöst wird, können Sie platzieren die **AllowPartiallyTrustedCallersAttribute** -Attribut im assemblygültigkeitsbereich einer freigegebenen -Bibliothek. Dieses Attribut ermöglicht, dass Ihre Bibliotheken aus teilweise vertrauenswürdigem verwaltetem Code heraus aufgerufen werden können.  
  
- Teilweise vertrauenswürdiger Code, dem durch dieses Attribut Zugriff auf eine Bibliothek gewährt wird, unterliegt nach wie vor weiteren Beschränkungen, die durch die <xref:System.AppDomain> definiert sind.  
  
- Es gibt keine programmgesteuerte Möglichkeit für teilweise vertrauenswürdigen Code zum Aufrufen einer Bibliothek, die nicht die **AllowPartiallyTrustedCallersAttribute** Attribut.  
  
 Bibliotheken, die für eine bestimmte Anwendung privat sind, erfordern keine starken Namen oder die **AllowPartiallyTrustedCallersAttribute** Attribut, und kann nicht durch potenziell bösartigen Code außerhalb der Anwendung verwiesen werden. Solcher Code ist gegen beabsichtigten oder unbeabsichtigten Missbrauch durch teilweise vertrauenswürdigen mobilen Code geschützt, ohne dass Entwickler zusätzlich aktiv werden müssen.  
  
 Bei folgenden Codetypen sollten Sie in Betracht ziehen, die Verwendung durch teilweise vertrauenswürdigen Code explizit zuzulassen:  
  
- Code, der sorgfältig auf Sicherheitsrisiken getestet wurde und wird in Übereinstimmung mit den Richtlinien unter [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md).  
  
- Codebibliotheken mit starkem Namen, die speziell für Szenarios geschrieben wurden, in denen teilweise Vertrauenswürdigkeit zu beachten ist.  
  
- Alle (teilweise oder vollständig vertrauenswürdigen) Komponenten, die mit einem starken Namen signiert sind und von Code aufgerufen werden, der aus dem Internet heruntergeladen wurde.  
  
> [!NOTE]
>  Einige Klassen in der .NET Framework-Klassenbibliothek müssen nicht die **AllowPartiallyTrustedCallersAttribute** Attribut, und kann nicht von teilweise vertrauenswürdigem Code aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch

- [Codezugriffssicherheit](../../../docs/framework/misc/code-access-security.md)
