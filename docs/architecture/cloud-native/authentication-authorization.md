---
title: Authentifizierung und Autorisierung in Cloud-Native apps
description: Architektur von Cloud Native .net-apps für Azure | Authentifizierung und Autorisierung in nativen Cloud-apps
ms.date: 05/13/2020
ms.openlocfilehash: e5254560ac82662e5e3ea6a25997516cd2b478b0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614304"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>Authentifizierung und Autorisierung in cloudbasierten Apps

Die *Authentifizierung* ist der Prozess der Bestimmung der Identität eines Sicherheits Prinzipals. Die *Autorisierung* ist das Erteilen einer authentifizierten Prinzipal Berechtigung zum Ausführen einer Aktion oder des Zugriffs auf eine Ressource. Manchmal wird die Authentifizierung auf verkürzt `AuthN` und die Autorisierung auf verkürzt `AuthZ` . Cloud native-Anwendungen müssen auf Open http-basierten Protokollen zum Authentifizieren von Sicherheits Prinzipalen basieren, da sowohl Clients als auch Anwendungen auf beliebigen Plattformen oder Geräten weltweit ausgeführt werden können. Der einzige häufige Faktor ist http.

Viele Organisationen verlassen sich weiterhin auf lokale Authentifizierungsdienste wie Active Directory-Verbunddienste (AD FS) (ADFS). Obwohl dieser Ansatz Organisationen traditionell für lokale Authentifizierungsanforderungen bereitgestellt hat, profitieren Native cloudanwendungen von Systemen, die speziell für die Cloud entwickelt wurden. In einer kürzlich erfolgten Empfehlung des US-amerikanischen National Cyber Security Centers (NCSC) 2019 im Vereinigten Königreich wird das Risiko im Vergleich zu ADFS durch Organisationen, die Azure AD als primäre Authentifizierungs Quelle verwenden, tatsächlich gesenkt. Einige der in [dieser Analyse](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) beschriebenen Gründe sind:

- Zugriff auf den vollständigen Satz von Microsoft-Technologien zum Schutz von Anmelde Informationen.
- Die meisten Organisationen verlassen sich bereits in gewissem Umfang auf Azure AD.
- Ein doppeltes Hashwert von NTLM-Hashes gewährleistet, dass keine Anmelde Informationen zugelassen werden, die in lokalen Active Directory funktionieren.

## <a name="references"></a>Referenzen

- [Authentifizierungsgrundlagen](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [Zugriffs Token und Ansprüche](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [Möglicherweise ist es an der Zeit, ihre lokalen Authentifizierungsdienste zu verwerfen.](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[Zurück](identity.md)
>[Weiter](azure-active-directory.md)
