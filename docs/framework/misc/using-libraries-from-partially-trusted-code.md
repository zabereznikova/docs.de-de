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
ms.openlocfilehash: 61291a07639c3f92a05f78dff49f6b20f1aee77e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645721"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
> Dieses Thema behandelt das Verhalten von Assemblys mit starkem Namen und gilt nur für Assemblys [der Ebene 1.](security-transparent-code-level-1.md) [Sicherheitstransparenter Code, Level](security-transparent-code-level-2.md) 2-Assemblys in .NET Framework 4 oder höher sind von starken Namen nicht betroffen. Weitere Informationen zu Änderungen am Sicherheitssystem finden Sie unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).  
  
 Anwendungen, die vom Host oder Sandkasten keine vollständige Vertrauenswürdigkeit erhalten, dürfen keine gemeinsam verwendeten verwalteten Bibliotheken aufrufen, es sei denn, der Entwickler der Bibliothek hat dies ausdrücklich durch Verwenden des <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attributs zugelassen. Anwendungsentwickler müssen daher beachten, dass ihnen aus einem teilweise vertrauenswürdigen Kontext einige Bibliotheken nicht zur Verfügung stehen. Standardmäßig ist der gesamte Code, der in einer [teilvertrauenswürdigen Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md) ausgeführt wird und nicht in der Liste der Assemblys mit voller Vertrauenswürdigkeit aufgeführt ist, teilweise vertrauenswürdig. Wenn Sie nicht erwarten, dass Ihr Code aus einem teilweise vertrauenswürdigen Kontext heraus ausgeführt oder aus teilweise vertrauenswürdigem Code aufgerufen wird, müssen Sie die Informationen in diesem Abschnitt nicht beachten. Wenn Sie jedoch Code schreiben, der mit teilweise vertrauenswürdigem Code zusammenwirken oder aus einem teilweise vertrauenswürdigen Kontext ausgeführt werden muss, sollten Sie folgende Faktoren berücksichtigen:  
  
- Bibliotheken müssen mit einem starken Namen signiert sein, damit sie von mehreren Anwendungen gemeinsam genutzt werden können. Starke Namen ermöglichen, dass Ihr Code im globalen Assemblycache platziert oder zur Liste für vollständige Vertrauenswürdigkeit einer Sandkasten-<xref:System.AppDomain> hinzugefügt werden kann, und ermöglichen Kunden festzustellen, dass ein bestimmter Teil mobilen Codes tatsächlich von Ihnen stammt.  
  
- Standardmäßig führen freigegebene [Bibliotheken](security-transparent-code-level-1.md) mit starkem Namen der Ebene 1 automatisch eine implizite [LinkDemand](link-demands.md) für volle Vertrauenswürdigkeit aus, ohne dass der Bibliotheksschreiber etwas tun muss.  
  
- Wenn ein Aufrufer nicht vollständig vertrauenswürdig ist, aber trotzdem versucht, eine solche Bibliothek aufzurufen, löst die Runtime eine <xref:System.Security.SecurityException> aus, und der Aufrufer kann keine Verbindung mit der Bibliothek herstellen  
  
- Um die automatische **LinkDemand** zu deaktivieren und zu verhindern, dass die Ausnahme ausgelöst wird, können Sie das **AllowPartiallyTrustedCallersAttribute-Attribut** im Assemblybereich einer freigegebenen Bibliothek platzieren. Dieses Attribut ermöglicht, dass Ihre Bibliotheken aus teilweise vertrauenswürdigem verwaltetem Code heraus aufgerufen werden können.  
  
- Teilweise vertrauenswürdiger Code, dem durch dieses Attribut Zugriff auf eine Bibliothek gewährt wird, unterliegt nach wie vor weiteren Beschränkungen, die durch die <xref:System.AppDomain> definiert sind.  
  
- Es gibt keine programmgesteuerte Möglichkeit für teilweise vertrauenswürdigen Code, eine Bibliothek aufzurufen, die nicht über das **AllowPartiallyTrustedCallersAttribute-Attribut** verfügt.  
  
 Bibliotheken, die für eine bestimmte Anwendung privat sind, benötigen keinen starken Namen oder das **AllowPartiallyTrustedCallersAttribute-Attribut** und können nicht von potenziell schädlichem Code außerhalb der Anwendung referenziert werden. Solcher Code ist gegen beabsichtigten oder unbeabsichtigten Missbrauch durch teilweise vertrauenswürdigen mobilen Code geschützt, ohne dass Entwickler zusätzlich aktiv werden müssen.  
  
 Bei folgenden Codetypen sollten Sie in Betracht ziehen, die Verwendung durch teilweise vertrauenswürdigen Code explizit zuzulassen:   
  
- Code, der sorgfältig auf Sicherheitslücken getestet wurde und den richtlinien entspricht, die in [Secure Coding Guidelines](../../standard/security/secure-coding-guidelines.md)beschrieben sind.  
  
- Codebibliotheken mit starkem Namen, die speziell für Szenarios geschrieben wurden, in denen teilweise Vertrauenswürdigkeit zu beachten ist.  
  
- Alle (teilweise oder vollständig vertrauenswürdigen) Komponenten, die mit einem starken Namen signiert sind und von Code aufgerufen werden, der aus dem Internet heruntergeladen wurde.  
  
> [!NOTE]
> Einige Klassen in der .NET Framework-Klassenbibliothek verfügen nicht über das **AllowPartiallyTrustedCallersAttribute-Attribut** und können nicht von teilweise vertrauenswürdigem Code aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch

- [Codezugriffssicherheit](code-access-security.md)
