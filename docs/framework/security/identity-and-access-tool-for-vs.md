---
title: Identitäts- und Zugriffs-Tool für Visual Studio 2012
ms.date: 03/30/2017
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
author: BrucePerlerMS
ms.openlocfilehash: d58cca13dc3ac67742e5371aed628a6a680e61e1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045416"
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a>Identitäts- und Zugriffs-Tool für Visual Studio 2012
In diesem Thema wird das neue Identitäts- und Zugriffs-Tool für Visual Studio 11 beschrieben. Sie können dieses Tool von folgender URL herunterladen: <https://go.microsoft.com/fwlink/?LinkID=245849> oder direkt in Visual Studio 11, indem Sie direkt im Erweiterungs-Manager nach "Identität" suchen.  
  
 Das Identitäts- und Zugriffs-Tool für Visual Studio 11 bietet eine vereinfachte Entwicklungserfahrung mit folgenden Vorteilen:  
  
- Mithilfe des neuen Tools können Sie Webanwendungsprojekttypen für die Entwicklung und IIS Express als Ziel verwenden.  
  
- Anders als bei der pauschalen Authentifizierung können Sie mit dem neuen Tool die lokale Startseitenbereich-Discovery-Seite bzw. den Controller (oder einen anderen Endpunkt, der für die Authentifizierungserfahrung innerhalb der Anwendung zuständig ist) angeben. WIF konfiguriert dann alle nicht authentifizierten Anforderungen für diesen Endpunkt, anstatt sie an den STS umzuleiten.  
  
- Das Tool enthält einen Test-Sicherheitstokendienst (STS), der auf dem lokalen Computer ausgeführt wird, wenn Sie eine Debugsitzung starten. Daher müssen Sie keine benutzerdefinierten STS-Projekte mehr erstellen und ändern, um die Ansprüche abzurufen, die Sie zum Testen der Anwendungen benötigen. Die Anspruchstypen und -werte sind vollständig anpassbar.  
  
- Sie können allgemeine Einstellungen direkt über die Benutzeroberfläche des Tools ändern, ohne die Datei web.config zu bearbeiten.  
  
- Sie können den Verbund mit Active Directory-Verbunddiensten (AD FS) 2.0 (oder mit anderen WS-Verbund-Anbietern) in nur einem Bildschirm erstellen.  
  
- Das Tool nutzt die Funktionen von Windows Azure Access Control Service (ACS) mit einer einfachen Liste von Kontrollkästchen für alle Identitäts Anbieter, die Sie verwenden möchten: Facebook, Google, Live ID, Yahoo!, ein beliebiger OpenID-Anbieter und ein beliebiger WS-Verbund-Anbieter. Wählen Sie die Identitätsanbieter aus, klicken Sie auf "OK", und drücken Sie F5. Daraufhin werden die Anwendung und ACS automatisch konfiguriert und die Testanwendung ist ACS-fähig.  
  
## <a name="see-also"></a>Siehe auch

- [WIF-Features](wif-features.md)
