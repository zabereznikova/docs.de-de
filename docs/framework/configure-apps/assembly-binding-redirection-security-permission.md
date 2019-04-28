---
title: Sicherheitsberechtigung für die Umleitung der Assemblybindung
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: ba4e7e790860696f4489e9ef7b73bddcb8c4e399
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705427"
---
# <a name="assembly-binding-redirection-security-permission"></a>Sicherheitsberechtigung für die Umleitung der Assemblybindung
Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich. Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern. Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>. Verwaltete Assemblys verfügen standardmäßig über keine Berechtigungen zu.  
  
 Anwendungen, die in der Zone der vertrauenswürdigen (lokaler Computer) und der Intranetzone ausgeführt wird die Sicherheitsberechtigung gewährt. Anwendungen, die in der Internetzone ausgeführt werden streng untersagt, von der Durchführung der Umleitung der Assemblybindung.  
  
 Die Berechtigung ist nicht erforderlich, wenn Assemblyumleitungen durchgeführt wird, in eine Herausgeberrichtliniendatei, die von der Komponentenherausgeber gesteuert wird, oder in der Konfigurationsdatei des Computers ein, die vom Administrator gesteuert wird. Die Berechtigung ist jedoch erforderlich, damit eine Anwendung explizit ignoriert Herausgeberrichtlinie mithilfe der [ \<PublisherPolicy anwenden = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) Element in der Konfigurationsdatei der Anwendung.  
  
 Die folgende Tabelle zeigt die Sicherheitseinstellungen für die **BindingRedirects** Flag.  
  
|Zone|BindingRedirects-Flags|  
|----------|-----------------------------------|  
|Vertrauenswürdigen Zone (lokaler Computer)|**ON**|  
|Intranetzone|**ON**|  
|Internetzone|**OFF**|  
|Nicht vertrauenswürdige Zonen|**OFF**|  
  
 Diese Sicherheitseinstellungen für die Unterstützung oder bestimmte Szenarien auf einem Computer zu beschränken, kann ein Administrator ändern. Es sind keine Tools zum Ändern der **BindingRedirects** Flag, das auf den Standard die Security.config-Datei auf dem Computer eines Benutzers muss von ein Administrator manuell bearbeiten.  
  
## <a name="see-also"></a>Siehe auch

- [Herausgeberrichtliniendateien und Seite-an-Seite-Ausführung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))
- [Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
- [Parallele Ausführung](../../../docs/framework/deployment/side-by-side-execution.md)
