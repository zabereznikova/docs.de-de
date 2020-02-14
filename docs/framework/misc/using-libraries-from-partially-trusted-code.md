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
ms.openlocfilehash: 6836d6c7f67afba316125b57b2c3e64a59ac648f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216989"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
> Dieses Thema behandelt das Verhalten von Assemblys mit starkem Namen und gilt nur für Assemblys der [Ebene 1](security-transparent-code-level-1.md) . [Sicherheits transparenter Code, ebenen2-](security-transparent-code-level-2.md) Assemblys in den .NET Framework 4 oder höher sind von starken Namen nicht betroffen. Weitere Informationen zu Änderungen am Sicherheitssystem finden Sie unter [Sicherheitsänderungen](../security/security-changes.md).  
  
 Anwendungen, die vom Host oder Sandkasten keine vollständige Vertrauenswürdigkeit erhalten, dürfen keine gemeinsam verwendeten verwalteten Bibliotheken aufrufen, es sei denn, der Entwickler der Bibliothek hat dies ausdrücklich durch Verwenden des <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attributs zugelassen. Anwendungsentwickler müssen daher beachten, dass ihnen aus einem teilweise vertrauenswürdigen Kontext einige Bibliotheken nicht zur Verfügung stehen. Standardmäßig ist der gesamte Code, der in einer teilweise vertrauenswürdigen [Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md) ausgeführt wird und nicht in der Liste der vollständig vertrauenswürdigen Assemblys enthalten ist, teilweise vertrauenswürdig. Wenn Sie nicht erwarten, dass Ihr Code aus einem teilweise vertrauenswürdigen Kontext heraus ausgeführt oder aus teilweise vertrauenswürdigem Code aufgerufen wird, müssen Sie die Informationen in diesem Abschnitt nicht beachten. Wenn Sie jedoch Code schreiben, der mit teilweise vertrauenswürdigem Code zusammenwirken oder aus einem teilweise vertrauenswürdigen Kontext ausgeführt werden muss, sollten Sie folgende Faktoren berücksichtigen:  
  
- Bibliotheken müssen mit einem starken Namen signiert sein, damit sie von mehreren Anwendungen gemeinsam genutzt werden können. Starke Namen ermöglichen, dass Ihr Code im globalen Assemblycache platziert oder zur Liste für vollständige Vertrauenswürdigkeit einer Sandkasten-<xref:System.AppDomain> hinzugefügt werden kann, und ermöglichen Kunden festzustellen, dass ein bestimmter Teil mobilen Codes tatsächlich von Ihnen stammt.  
  
- Standardmäßig führen freigegebene Bibliotheken mit starkem Namen auf [Ebene 1](security-transparent-code-level-1.md) einen impliziten [LinkDemand](link-demands.md) für vollständige Vertrauenswürdigkeit aus, ohne dass der bibliothekswriter etwas tun muss.  
  
- Wenn ein Aufrufer nicht vollständig vertrauenswürdig ist, aber trotzdem versucht, eine solche Bibliothek aufzurufen, löst die Runtime eine <xref:System.Security.SecurityException> aus, und der Aufrufer kann keine Verbindung mit der Bibliothek herstellen  
  
- Um die automatische **LinkDemand** zu deaktivieren und zu verhindern, dass die Ausnahme ausgelöst wird, können Sie das **allowpartiallytrust dcallersattribute** -Attribut für den Assemblybereich einer freigegebenen Bibliothek platzieren. Dieses Attribut ermöglicht, dass Ihre Bibliotheken aus teilweise vertrauenswürdigem verwaltetem Code heraus aufgerufen werden können.  
  
- Teilweise vertrauenswürdiger Code, dem durch dieses Attribut Zugriff auf eine Bibliothek gewährt wird, unterliegt nach wie vor weiteren Beschränkungen, die durch die <xref:System.AppDomain> definiert sind.  
  
- Es gibt keine programmgesteuerte Möglichkeit für teilweise vertrauenswürdigen Code, eine Bibliothek aufzurufen, die nicht über das **allowpartiallytrust dcallersattribute** -Attribut verfügt.  
  
 Bibliotheken, die für eine bestimmte Anwendung privat sind, benötigen keinen starken Namen oder das **allowpartiallytrust dcallersattribute** -Attribut, und es kann nicht von potenziell bösartigem Code außerhalb der Anwendung auf Sie verwiesen werden. Solcher Code ist gegen beabsichtigten oder unbeabsichtigten Missbrauch durch teilweise vertrauenswürdigen mobilen Code geschützt, ohne dass Entwickler zusätzlich aktiv werden müssen.  
  
 Bei folgenden Codetypen sollten Sie in Betracht ziehen, die Verwendung durch teilweise vertrauenswürdigen Code explizit zuzulassen:  
  
- Code, der sorgfältig auf Sicherheitsrisiken getestet wurde und mit den Richtlinien konform ist, die unter [Richtlinien für sicheres Program](../../standard/security/secure-coding-guidelines.md)mieren beschrieben werden.  
  
- Codebibliotheken mit starkem Namen, die speziell für Szenarios geschrieben wurden, in denen teilweise Vertrauenswürdigkeit zu beachten ist.  
  
- Alle (teilweise oder vollständig vertrauenswürdigen) Komponenten, die mit einem starken Namen signiert sind und von Code aufgerufen werden, der aus dem Internet heruntergeladen wurde.  
  
> [!NOTE]
> Einige Klassen in der .NET Framework-Klassenbibliothek haben nicht das **allowpartiallytrust dcallersattribute** -Attribut und können nicht von teilweise vertrauenswürdigem Code aufgerufen werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Codezugriffssicherheit](code-access-security.md)
