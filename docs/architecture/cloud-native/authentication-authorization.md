---
title: Authentifizierung und Autorisierung in Cloud-nativen Apps
description: Architektur von Cloud Native .NET-Apps für Azure | Authentifizierung und Autorisierung in Cloud Native Apps
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805546"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>Authentifizierung und Autorisierung in cloudbasierten Apps

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Bei der *Authentifizierung* wird die Identität eines Sicherheitsprinzipals ermittelt. *Die Autorisierung* ist der Akt, bei dem eine authentifizierte Prinzipalberechtigung zum Ausführen einer Aktion oder zum Zugriff auf eine Ressource erteilt wird. Manchmal wird die `AuthN` Authentifizierung verkürzt `AuthZ`und die Autorisierung auf . Cloud-native Anwendungen müssen sich auf offene HTTP-basierte Protokolle verlassen, um Sicherheitsprinzipale zu authentifizieren, da sowohl Clients als auch Anwendungen auf jeder Plattform oder jedem Gerät überall auf der Welt ausgeführt werden können. Der einzige häufige Faktor ist HTTP.

Viele Organisationen verlassen sich weiterhin auf lokale Authentifizierungsdienste wie Active Directory Federation Services (ADFS). Während dieser Ansatz Unternehmen traditionell gut für lokale Authentifizierungsanforderungen eignet, profitieren Cloud-native Anwendungen von Systemen, die speziell für die Cloud entwickelt wurden. In einer kürzlich veröffentlichten Empfehlung des United Kingdom National Cyber Security Centre (NCSC) aus dem Jahr 2019 heißt es, dass "Organisationen, die Azure AD als primäre Authentifizierungsquelle verwenden, ihr Risiko im Vergleich zu ADFS tatsächlich senken werden." Zu den in [dieser Analyse](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) beschriebenen Gründen gehören:

- Zugriff auf den vollständigen Satz von Microsoft-Technologien zum Schutz von Anmeldeinformationen.
- Die meisten Organisationen verlassen sich bereits in gewissem Maße auf Azure AD.
- Doppeltes Hashing von NTLM-Hashes stellt sicher, dass eine Gefährdung keine Anmeldeinformationen zulässt, die in lokalem Active Directory funktionieren.

## <a name="references"></a>References

- [Authentifizierungsgrundlagen](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [Zugriff auf Token und Ansprüche](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [Es kann an der Zeit sein, Ihre lokalen Authentifizierungsdienste zu verwerfen](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[Zurück](identity.md)
>[Weiter](azure-active-directory.md)
