---
title: Sicherheitsfunktionen mit benutzerdefinierten Bindungen
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 1b12907481ccb3f3c5f4b8aaba6ede8ebfa6228a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288306"
---
# <a name="security-capabilities-with-custom-bindings"></a>Sicherheitsfunktionen mit benutzerdefinierten Bindungen

Sie können die meisten der allgemeinen Sicherheitsaufgaben mithilfe einer vom System bereitgestellten Bindung ausführen. Wenn Sie die Sicherheit jedoch detaillierter steuern müssen, können Sie mit <xref:System.ServiceModel.Channels.SecurityBindingElement> eine benutzerdefinierte Bindung erstellen, wie in diesen Themen erläutert. Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [SecurityBindingElement-Authentifizierungsmodi](securitybindingelement-authentication-modes.md)  
 Beschreibt die Authentifizierungsmodi, die mit einer benutzerdefinierten Bindung möglich sind.  
  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Beschreibt die grundlegenden Schritte zum Erstellen einer benutzerdefinierten Bindung mit einem Sicherheitselement.  
  
 [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Beschreibt das Erstellen eines Sicherheitselements für einen angegebenen Authentifizierungsmodus.  
  
 [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Beschreibt das Deaktivieren von Sicherheitssitzungen beim Erstellen eines Verbunddienstes.  
  
 [Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung](how-to-enable-message-replay-detection.md)  
 Beschreibt, wie ein Replay-Angriff entdeckt werden kann.  
  
 [Vorgehensweise: Erstellen unterstützender Anmeldeinformationen](how-to-create-a-supporting-credential.md)  
 Beschreibt das Bereitstellen unterstützender Anmeldeinformationen für einen Dienst, wenn sie vom Dienst benötigt werden.  
  
 [Vorgehensweise: Einrichten einer Signaturbestätigung](how-to-set-up-a-signature-confirmation.md)  
 Beschreibt die Schritte zum Bestätigen von Signaturen beim digitalen Signieren von Nachrichten.  
  
 [Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)](how-to-set-a-max-clock-skew.md)  
 Beschreibt das Festlegen des maximal zulässigen Zeitunterschieds zwischen einem Dienst und einem Client.  
  
 [Vorgehensweise: Deaktivieren der Verschlüsselung digitaler Signaturen](how-to-disable-encryption-of-digital-signatures.md)  
 Beschreibt, inwiefern das Deaktivieren der Verschlüsselung von digitalen Signaturen die Leistung verbessern kann.  
  
## <a name="reference"></a>Referenz  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Grundlagen der Schutzebene](../understanding-protection-level.md)  
  
 [Sichern von Diensten und Clients](securing-services-and-clients.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Bindungen und Sicherheit](bindings-and-security.md)
- [Sicherheitsübersicht](security-overview.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
