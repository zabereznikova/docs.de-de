---
title: Azure Active Directory
description: Architektur von Cloud Native .net-apps für Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 03f5ea8e84bc3c4a2a88a63d4b109aabf0c64f36
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614278"
---
# <a name="azure-active-directory"></a>Azure Active Directory

Microsoft Azure Active Directory (Azure AD) bietet Identitäts-und Zugriffs Verwaltung als Dienst. Kunden verwenden Sie, um zu konfigurieren und zu warten, wer Benutzer sind, welche Informationen über Sie gespeichert werden, wer auf diese Informationen zugreifen kann, wer Sie verwalten kann und auf welche apps Sie zugreifen können. Aad kann Benutzer für Anwendungen authentifizieren, die für die Verwendung konfiguriert sind, und bietet eine Single Sign-on (SSO). Sie kann eigenständig verwendet oder in Windows AD integriert werden, das lokal ausgeführt wird.

Azure AD für die Cloud erstellt. Es handelt sich tatsächlich um eine cloudbasierte Identitäts Lösung, die eine Rest-basierte Graph-API und odata-Syntax für Abfragen verwendet, anders als Windows AD, bei dem LDAP verwendet wird. Lokale Active Directory können Benutzerattribute mithilfe von Identitäts Synchronisierungs Diensten in der Cloud synchronisieren, sodass die gesamte Authentifizierung mithilfe Azure AD in der Cloud erfolgen kann. Alternativ kann die Authentifizierung über Connect konfiguriert werden, um Sie über AD FS zurück an lokale Active Directory zu übergeben, um von Windows AD lokal abgeschlossen zu werden.

Azure Ad unterstützt Unternehmens Branding-Anmelde Bildschirme, Multi-Factory-Authentifizierung und cloudbasierte Anwendungs Proxys, die verwendet werden, um SSO für Lokal gehostete Anwendungen bereitzustellen. Sie bietet verschiedene Arten von Sicherheitsberichten und Warnungs Funktionen.

## <a name="references"></a>Referenzen

- [Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Zurück](authentication-authorization.md)
>[Weiter](identity-server.md)
